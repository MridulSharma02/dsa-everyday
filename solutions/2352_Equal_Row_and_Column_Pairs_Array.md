<div align="center">

# 📦 2352. Equal Row and Column Pairs

*Pushed on July 12, 2026 · Problem #35 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 71.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Hash Table` `Matrix` `Simulation`

---

## 🧩 Problem Description

Given a **0-indexed** `n x n` integer matrix `grid`, *return the number of pairs *`(ri, cj)`* such that row *`ri`* and column *`cj`* are equal*.


A row and column pair is considered equal if they contain the same elements in the same order (i.e., an equal array).


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2022/06/01/ex1.jpg" style="width: 150px; height: 153px;" />

**Input:** grid = [[3,2,1],[1,7,6],[2,7,7]]
**Output:** 1
**Explanation:** There is 1 equal row and column pair:
- (Row 2, Column 1): [2,7,7]


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2022/06/01/ex2.jpg" style="width: 200px; height: 209px;" />

**Input:** grid = [[3,1,2,2],[1,4,4,5],[2,4,2,2],[2,4,2,2]]
**Output:** 3
**Explanation:** There are 3 equal row and column pairs:
- (Row 0, Column 0): [3,1,2,2]
- (Row 2, Column 2): [2,4,2,2]
- (Row 3, Column 2): [2,4,2,2]


 

**Constraints:**



	- `n == grid.length == grid[i].length`
	- `1 <= n <= 200`
	- `1 <= grid[i][j] <= 10^5`

---

## 🪄 Hints
> 💡 We can use nested loops to compare every row against every column.
> 💡 Another loop is necessary to compare the row and column element by element.

## 💻 My Solution

```python
class Solution(object):
    def equalPairs(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        n = len(grid)

        rows = {}
        for row in grid:
            t = tuple(row)
            rows[t] = rows.get(t, 0) + 1

        ans = 0

        for c in range(n):
            col = tuple(grid[r][c] for r in range(n))
            ans += rows.get(col, 0)

        return ans       

```

---

## 🧪 Sample Test Case

```
[[3,2,1],[1,7,6],[2,7,7]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
