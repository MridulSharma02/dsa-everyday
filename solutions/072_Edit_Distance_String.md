<div align="center">

# 🔤 72. Edit Distance

*Pushed on July 04, 2026 · Problem #27 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 60.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Dynamic Programming`

---

## 🧩 Problem Description

Given two strings `word1` and `word2`, return *the minimum number of operations required to convert `word1` to `word2`*.


You have the following three operations permitted on a word:



	- Insert a character
	- Delete a character
	- Replace a character


 

<strong class="example">Example 1:**



**Input:** word1 = &quot;horse&quot;, word2 = &quot;ros&quot;
**Output:** 3
**Explanation:** 
horse -> rorse (replace &#39;h&#39; with &#39;r&#39;)
rorse -> rose (remove &#39;r&#39;)
rose -> ros (remove &#39;e&#39;)


<strong class="example">Example 2:**



**Input:** word1 = &quot;intention&quot;, word2 = &quot;execution&quot;
**Output:** 5
**Explanation:** 
intention -> inention (remove &#39;t&#39;)
inention -> enention (replace &#39;i&#39; with &#39;e&#39;)
enention -> exention (replace &#39;n&#39; with &#39;x&#39;)
exention -> exection (replace &#39;n&#39; with &#39;c&#39;)
exection -> execution (insert &#39;u&#39;)


 

**Constraints:**



	- `0 <= word1.length, word2.length <= 500`
	- `word1` and `word2` consist of lowercase English letters.

---

## 💻 My Solution

```cpp
class Solution {
public:
    int minDistance(string word1, string word2) {
        int m = word1.size(), n = word2.size();
        vector<vector<int>> dp(m + 1, vector<int>(n + 1));

        for (int i = 0; i <= m; i++) dp[i][0] = i;
        for (int j = 0; j <= n; j++) dp[0][j] = j;

        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                if (word1[i - 1] == word2[j - 1]) {
                    dp[i][j] = dp[i - 1][j - 1];
                } else {
                    dp[i][j] = 1 + min({dp[i - 1][j], dp[i][j - 1], dp[i - 1][j - 1]});
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
"horse"
"ros"
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
