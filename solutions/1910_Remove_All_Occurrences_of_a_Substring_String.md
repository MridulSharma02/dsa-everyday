<div align="center">

# 🔤 1910. Remove All Occurrences of a Substring

*Pushed on November 24, 2026 · Problem #169 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 78.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Stack` `Simulation`

---

## 🧩 Problem Description

Given two strings `s` and `part`, perform the following operation on `s` until **all** occurrences of the substring `part` are removed:



	- Find the **leftmost** occurrence of the substring `part` and **remove** it from `s`.


Return `s`* after removing all occurrences of *`part`.


A **substring** is a contiguous sequence of characters in a string.


 

<strong class="example">Example 1:**



**Input:** s = &quot;daabcbaabcbc&quot;, part = &quot;abc&quot;
**Output:** &quot;dab&quot;
**Explanation**: The following operations are done:
- s = &quot;da**<u>abc</u>**baabcbc&quot;, remove &quot;abc&quot; starting at index 2, so s = &quot;dabaabcbc&quot;.
- s = &quot;daba**<u>abc</u>**bc&quot;, remove &quot;abc&quot; starting at index 4, so s = &quot;dababc&quot;.
- s = &quot;dab**<u>abc</u>**&quot;, remove &quot;abc&quot; starting at index 3, so s = &quot;dab&quot;.
Now s has no occurrences of &quot;abc&quot;.


<strong class="example">Example 2:**



**Input:** s = &quot;axxxxyyyyb&quot;, part = &quot;xy&quot;
**Output:** &quot;ab&quot;
**Explanation**: The following operations are done:
- s = &quot;axxx**<u>xy</u>**yyyb&quot;, remove &quot;xy&quot; starting at index 4 so s = &quot;axxxyyyb&quot;.
- s = &quot;axx**<u>xy</u>**yyb&quot;, remove &quot;xy&quot; starting at index 3 so s = &quot;axxyyb&quot;.
- s = &quot;ax**<u>xy</u>**yb&quot;, remove &quot;xy&quot; starting at index 2 so s = &quot;axyb&quot;.
- s = &quot;a**<u>xy</u>**b&quot;, remove &quot;xy&quot; starting at index 1 so s = &quot;ab&quot;.
Now s has no occurrences of &quot;xy&quot;.


 

**Constraints:**



	- `1 <= s.length <= 1000`
	- `1 <= part.length <= 1000`
	- `s`​​​​​​ and `part` consists of lowercase English letters.

---

## 🪄 Hints
> 💡 Note that a new occurrence of pattern can appear if you remove an old one, For example, s = "ababcc" and pattern = "abc".
> 💡 You can maintain a stack of characters and if the last character of the pattern size in the stack match the pattern remove them

## 💻 My Solution

```cpp
class Solution {
public:
    string removeOccurrences(string s, string part) {
        int n = part.size();
        vector<int> lps(n, 0);
        for (int i=1,len=0;i<n; ){
            if(part[i]==part[len]){
                lps[i++]=++len;
            }else if(len>0){
                len=lps[len-1];
            }else{
                lps[i++]=0;
            }
        }

        string ans;
        vector<int> match;
        int len=0;
        for(char c:s){
            ans.push_back(c);
            while(len>0 && part[len]!=c){
                len=lps[len-1];
            }
            if(part[len]==c)
                len++;

            match.push_back(len);
            if(len==n){
                for(int i=0;i<n;i++){
                    ans.pop_back();
                }
                match.resize(match.size()-n);

                len=match.empty() ? 0: match.back();
            }
        }
        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"daabcbaabcbc"
"abc"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
