<div align="center">

# 👆 28. Find the Index of the First Occurrence in a String

*Pushed on October 18, 2026 · Problem #133 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 👆 Two Pointers   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 47.5%              |
| **Language**         | 🔠 C++         |

**Tags:** `Two Pointers` `String` `String Matching` `Z Algorithm` `Knuth–Morris–Pratt Algorithm` `Boyer–Moore String-Search Algorithm`

---

## 🧩 Problem Description

Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.


 

<strong class="example">Example 1:**



**Input:** haystack = &quot;sadbutsad&quot;, needle = &quot;sad&quot;
**Output:** 0
**Explanation:** &quot;sad&quot; occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.


<strong class="example">Example 2:**



**Input:** haystack = &quot;leetcode&quot;, needle = &quot;leeto&quot;
**Output:** -1
**Explanation:** &quot;leeto&quot; did not occur in &quot;leetcode&quot;, so we return -1.


 

**Constraints:**



	- `1 <= haystack.length, needle.length <= 10^4`
	- `haystack` and `needle` consist of only lowercase English characters.

---

## 💻 My Solution

```cpp
// Brute Force
//class Solution {
// public:
//     int strStr(string haystack, string needle) {
//         int n=haystack.size();
//         int m=needle.size();
//         for(int i=0;i<=n-m;i++){
//             int j=0;
//             while(j<m && haystack[i+j]==needle[j]){
//                 j++;
//             }
//             if(j==m)
//                 return i;
//         }

//         return -1;
//     }
// };

// KMP
class Solution{
public:
    int strStr(string haystack, string needle){
        int n=haystack.size();
        int m=needle.size();
        vector<int> lps(m,0);
        int len=0;
        int i=1;
        while(i<m){
            if(needle[i]==needle[len]){
                len++;
                lps[i]=len;
                i++;
            }
            else{
                if(len!=0){
                    len=lps[len-1];
                }
                else{
                    lps[i]=0;
                    i++;
                }
            }
        }
        i=0;
        int j=0;
        while(i<n){
            if(haystack[i]==needle[j]){
                i++;
                j++;
            }
            if(j==m)
                return i-j;
            else if(i<n && haystack[i]!=needle[j]){
                if(j!=0)
                    j=lps[j-1];
                else
                    i++;
            }
        }

        return -1;
    }
};

```

---

## 🧪 Sample Test Case

```
"sadbutsad"
"sad"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Two Pointers** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying two pointers to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
