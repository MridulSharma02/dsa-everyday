<div align="center">

# 🧬 790. Domino and Tromino Tiling

*Pushed on July 03, 2026 · Problem #26 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🧬 Dynamic Programming   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 51.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Dynamic Programming`

---

## 🧩 Problem Description

You have two types of tiles: a `2 x 1` domino shape and a tromino shape. You may rotate these shapes.

<img alt="" src="https://assets.leetcode.com/uploads/2021/07/15/lc-domino.jpg" style="width: 362px; height: 195px;" />
Given an integer n, return *the number of ways to tile an* `2 x n` *board*. Since the answer may be very large, return it **modulo** `10^9 + 7`.


In a tiling, every square must be covered by a tile. Two tilings are different if and only if there are two 4-directionally adjacent cells on the board such that exactly one of the tilings has both squares occupied by a tile.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/07/15/lc-domino1.jpg" style="width: 500px; height: 226px;" />

**Input:** n = 3
**Output:** 5
**Explanation:** The five different ways are shown above.


<strong class="example">Example 2:**



**Input:** n = 1
**Output:** 1


 

**Constraints:**



	- `1 <= n <= 1000`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int numTilings(int n) {
        const int MOD = 1e9 + 7;

        if (n == 1) return 1;
        if (n == 2) return 2;

        vector<long long> dp(n + 1);
        dp[0] = 1;
        dp[1] = 1;
        dp[2] = 2;

        for (int i = 3; i <= n; i++) {
            dp[i] = (2 * dp[i - 1] + dp[i - 3]) % MOD;
        }

        return dp[n];
    }
};

```

---

## 🧪 Sample Test Case

```
3
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Dynamic Programming** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying dynamic programming to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
