<div align="center">

# 🔤 10. Regular Expression Matching

*Pushed on November 22, 2026 · Problem #168 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 32.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Dynamic Programming` `Recursion`

---

## 🧩 Problem Description

Given an input string `s` and a pattern `p`, implement regular expression matching with support for `&#39;.&#39;` and `&#39;*&#39;` where:



	- `&#39;.&#39;` Matches any single character.​​​​
	- `&#39;*&#39;` Matches zero or more of the preceding element.


Return a boolean indicating whether the matching covers the entire input string (not partial).


 

<strong class="example">Example 1:**



**Input:** s = &quot;aa&quot;, p = &quot;a&quot;
**Output:** false
**Explanation:** &quot;a&quot; does not match the entire string &quot;aa&quot;.


<strong class="example">Example 2:**



**Input:** s = &quot;aa&quot;, p = &quot;a*&quot;
**Output:** true
**Explanation:** &#39;*&#39; means zero or more of the preceding element, &#39;a&#39;. Therefore, by repeating &#39;a&#39; once, it becomes &quot;aa&quot;.


<strong class="example">Example 3:**



**Input:** s = &quot;ab&quot;, p = &quot;.*&quot;
**Output:** true
**Explanation:** &quot;.*&quot; means &quot;zero or more (*) of any character (.)&quot;.


 

**Constraints:**



	- `1 <= s.length <= 20`
	- `1 <= p.length <= 20`
	- `s` contains only lowercase English letters.
	- `p` contains only lowercase English letters, `&#39;.&#39;`, and `&#39;*&#39;`.
	- It is guaranteed for each appearance of the character `&#39;*&#39;`, there will be a previous valid character to match.

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool isMatch(string s, string p) {
        int m = s.size(), n = p.size();

        vector<vector<bool>> dp(m + 1, vector<bool>(n + 1, false));
        dp[0][0] = true;

        for (int j = 2; j <= n; j++) {
            if (p[j - 1] == '*')
                dp[0][j] = dp[0][j - 2];
        }

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (p[j - 1] == '.' || p[j - 1] == s[i - 1]) {
                    dp[i][j] = dp[i - 1][j - 1];
                }
                else if (p[j - 1] == '*') {
                    dp[i][j] = dp[i][j - 2];

                    if (p[j - 2] == '.' || p[j - 2] == s[i - 1]) {
                        dp[i][j] = dp[i][j] || dp[i - 1][j];
                    }
                }
            }
        }

        return dp[m][n];
    }
};

```

---

## 🧪 Sample Test Case

```
"aa"
"a"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
