<div align="center">

# 🔤 1143. Longest Common Subsequence

*Pushed on September 09, 2026 · Problem #94 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 59.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Dynamic Programming` `Longest Common Subsequence`

---

## 🧩 Problem Description

Given two strings `text1` and `text2`, return *the length of their longest **common subsequence**. *If there is no **common subsequence**, return `0`.


A **subsequence** of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.



	- For example, `&quot;ace&quot;` is a subsequence of `&quot;abcde&quot;`.


A **common subsequence** of two strings is a subsequence that is common to both strings.


 

<strong class="example">Example 1:**



**Input:** text1 = &quot;abcde&quot;, text2 = &quot;ace&quot; 
**Output:** 3  
**Explanation:** The longest common subsequence is &quot;ace&quot; and its length is 3.


<strong class="example">Example 2:**



**Input:** text1 = &quot;abc&quot;, text2 = &quot;abc&quot;
**Output:** 3
**Explanation:** The longest common subsequence is &quot;abc&quot; and its length is 3.


<strong class="example">Example 3:**



**Input:** text1 = &quot;abc&quot;, text2 = &quot;def&quot;
**Output:** 0
**Explanation:** There is no such common subsequence, so the result is 0.


 

**Constraints:**



	- `1 <= text1.length, text2.length <= 1000`
	- `text1` and `text2` consist of only lowercase English characters.

---

## 🪄 Hints
> 💡 Try dynamic programming. 
DP[i][j] represents the longest common subsequence of text1[0 ... i] & text2[0 ... j].
> 💡 DP[i][j] = DP[i - 1][j - 1] + 1 , if text1[i] == text2[j]
DP[i][j] = max(DP[i - 1][j], DP[i][j - 1]) , otherwise

## 💻 My Solution

```cpp
class Solution {
public:
    int longestCommonSubsequence(string text1, string text2) {
        int m = text1.size(), n = text2.size();
        vector<vector<int>> dp(m + 1, vector<int>(n + 1, 0));

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (text1[i - 1] == text2[j - 1])
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                else
                    dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]);
            }
        }

        return dp[m][n];
    }
};

```

---

## 🧪 Sample Test Case

```
"abcde"
"ace"
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
