<div align="center">

# 📦 51. N-Queens

*Pushed on October 10, 2026 · Problem #125 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 76.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Backtracking` `Algorithm X`

---

## 🧩 Problem Description

The **n-queens** puzzle is the problem of placing `n` queens on an `n x n` chessboard such that no two queens attack each other.


Given an integer `n`, return *all distinct solutions to the **n-queens puzzle***. You may return the answer in **any order**.


Each solution contains a distinct board configuration of the n-queens&#39; placement, where `&#39;Q&#39;` and `&#39;.&#39;` both indicate a queen and an empty space, respectively.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/11/13/queens.jpg" style="width: 600px; height: 268px;" />

**Input:** n = 4
**Output:** [[&quot;.Q..&quot;,&quot;...Q&quot;,&quot;Q...&quot;,&quot;..Q.&quot;],[&quot;..Q.&quot;,&quot;Q...&quot;,&quot;...Q&quot;,&quot;.Q..&quot;]]
**Explanation:** There exist two distinct solutions to the 4-queens puzzle as shown above


<strong class="example">Example 2:**



**Input:** n = 1
**Output:** [[&quot;Q&quot;]]


 

**Constraints:**



	- `1 <= n <= 9`

---

## 💻 My Solution

```python
class Solution(object):
    def solveNQueens(self, n):
        result = []

        cols = set()
        diag1 = set()  # row - col
        diag2 = set()  # row + col

        board = [["."] * n for _ in range(n)]

        def backtrack(row):
            if row == n:
                result.append(["".join(r) for r in board])
                return

            for col in range(n):
                if col in cols or (row - col) in diag1 or (row + col) in diag2:
                    continue

                board[row][col] = "Q"
                cols.add(col)
                diag1.add(row - col)
                diag2.add(row + col)

                backtrack(row + 1)

                board[row][col] = "."
                cols.remove(col)
                diag1.remove(row - col)
                diag2.remove(row + col)

        backtrack(0)
        return result
        

```

---

## 🧪 Sample Test Case

```
4
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
