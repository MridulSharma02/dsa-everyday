<div align="center">

# 🗂️ 859. Buddy Strings

*Pushed on October 15, 2026 · Problem #130 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 34.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `String`

---

## 🧩 Problem Description

Given two strings `s` and `goal`, return `true`* if you can swap two letters in *`s`* so the result is equal to *`goal`*, otherwise, return *`false`*.*


Swapping letters is defined as taking two indices `i` and `j` (0-indexed) such that `i != j` and swapping the characters at `s[i]` and `s[j]`.



	- For example, swapping at indices `0` and `2` in `&quot;abcd&quot;` results in `&quot;cbad&quot;`.


 

<strong class="example">Example 1:**



**Input:** s = &quot;ab&quot;, goal = &quot;ba&quot;
**Output:** true
**Explanation:** You can swap s[0] = &#39;a&#39; and s[1] = &#39;b&#39; to get &quot;ba&quot;, which is equal to goal.


<strong class="example">Example 2:**



**Input:** s = &quot;ab&quot;, goal = &quot;ab&quot;
**Output:** false
**Explanation:** The only letters you can swap are s[0] = &#39;a&#39; and s[1] = &#39;b&#39;, which results in &quot;ba&quot; != goal.


<strong class="example">Example 3:**



**Input:** s = &quot;aa&quot;, goal = &quot;aa&quot;
**Output:** true
**Explanation:** You can swap s[0] = &#39;a&#39; and s[1] = &#39;a&#39; to get &quot;aa&quot;, which is equal to goal.


 

**Constraints:**



	- `1 <= s.length, goal.length <= 2 * 10^4`
	- `s` and `goal` consist of lowercase letters.

---

## 💻 My Solution

```cpp
// Brute Force
// class Solution {
// public:
//     bool buddyStrings(string s, string goal) {
//         if(s.size()!=goal.size())
//             return false;
//         for(int i=0;i<s.size();i++){
//             for(int j=i+1;j<s.size();j++){
//                 swap(s[i],s[j]);
//                 if(s==goal)
//                     return true;

//                 swap(s[i],s[j]);
//             }
//         }

//         return false;
//     }
// };

// Optimized
class Solution {
public:
    bool buddyStrings(string s, string goal) {
        if(s.size()!=goal.size())
            return false;

        int first=-1;
        int second=-1;
        for(int i=0;i<s.size();i++){
            if(s[i]!=goal[i]){
                if(first==-1)
                    first=i;
                else if(second==-1)
                    second=i;
                else
                    return false;
            }
        }

        if(first==-1){
            int freq[26]={0};
            for(char c:s){
                freq[c-'a']++;
                if(freq[c-'a']>=2)
                    return true;
            }

            return false;
        }
        if(second==-1)
            return false;

        return s[first]==goal[second] &&
               s[second]==goal[first];
    }
};

```

---

## 🧪 Sample Test Case

```
"ab"
"ba"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Hash Table** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying hash table to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
