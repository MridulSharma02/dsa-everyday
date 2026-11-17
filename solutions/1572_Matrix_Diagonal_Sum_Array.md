<div align="center">

# 📦 1572. Matrix Diagonal Sum

*Pushed on November 17, 2026 · Problem #162 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 84.7%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Matrix`

---

## 🧩 Problem Description

Given a square matrix `mat`, return the sum of the matrix diagonals.


Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/08/14/sample_1911.png" style="width: 336px; height: 174px;" />

**Input:** mat = [[**1**,2,**3**],
              [4,**5**,6],
              [**7**,8,**9**]]
**Output:** 25
**Explanation: **Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25
Notice that element mat[1][1] = 5 is counted only once.


<strong class="example">Example 2:**



**Input:** mat = [[**1**,1,1,**1**],
              [1,**1**,**1**,1],
              [1,**1**,**1**,1],
              [**1**,1,1,**1**]]
**Output:** 8


<strong class="example">Example 3:**



**Input:** mat = [[**5**]]
**Output:** 5


 

**Constraints:**



	- `n == mat.length == mat[i].length`
	- `1 <= n <= 100`
	- `1 <= mat[i][j] <= 100`

---

## 🪄 Hints
> 💡 There will be overlap of elements in the primary and secondary diagonals if and only if the length of the matrix is odd, which is at the center.

## 💻 My Solution

```cpp
class Solution {
public:
    int diagonalSum(vector<vector<int>>& mat) {
        int n = mat.size();
        int sum = 0;

        for (int i = 0; i < n; i++) {
            sum += mat[i][i];      
            sum += mat[i][n - 1 - i];
        }

        if (n % 2 == 1) {
            sum -= mat[n / 2][n / 2];
        }

        return sum;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1,2,3],[4,5,6],[7,8,9]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
