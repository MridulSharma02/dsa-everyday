<div align="center">

# 🔤 1392. Longest Happy Prefix

*Pushed on October 22, 2026 · Problem #137 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 54.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Rolling Hash` `String Matching` `Hash Function` `Z Algorithm` `Knuth–Morris–Pratt Algorithm`

---

## 🧩 Problem Description

A string is called a **happy prefix** if it is a **non-empty** prefix which is also a suffix (excluding itself).


Given a string `s`, return *the **longest happy prefix** of* `s`. Return an empty string `&quot;&quot;` if no such prefix exists.


 

<strong class="example">Example 1:**



**Input:** s = &quot;level&quot;
**Output:** &quot;l&quot;
**Explanation:** s contains 4 prefix excluding itself (&quot;l&quot;, &quot;le&quot;, &quot;lev&quot;, &quot;leve&quot;), and suffix (&quot;l&quot;, &quot;el&quot;, &quot;vel&quot;, &quot;evel&quot;). The largest prefix which is also suffix is given by &quot;l&quot;.


<strong class="example">Example 2:**



**Input:** s = &quot;ababab&quot;
**Output:** &quot;abab&quot;
**Explanation:** &quot;abab&quot; is the largest prefix which is also suffix. They can overlap in the original string.


 

**Constraints:**



	- `1 <= s.length <= 10^5`
	- `s` contains only lowercase English letters.

---

## 🪄 Hints
> 💡 Use Longest Prefix Suffix (KMP-table) or String Hashing.

## 💻 My Solution

```cpp
class Solution {
public:
    string longestPrefix(string s) {
        int n=s.size();
        vector<int> lps(n,0);
        int len=0;
        int i=1;
        while(i<n){
            if(s[i]==s[len]){
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

        string ans;
        for(int i=0;i<lps[n-1];i++){
            ans += s[i];
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"level"
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
