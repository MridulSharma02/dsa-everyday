<div align="center">

# 🔁 52. N-Queens II

*Pushed on October 09, 2026 · Problem #124 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🔁 Backtracking   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 79.5%              |
| **Language**         | 🔠 C++         |

**Tags:** `Backtracking` `Algorithm X`

---

## 🧩 Problem Description

The **n-queens** puzzle is the problem of placing `n` queens on an `n x n` chessboard such that no two queens attack each other.


Given an integer `n`, return *the number of distinct solutions to the **n-queens puzzle***.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/11/13/queens.jpg" style="width: 600px; height: 268px;" />

**Input:** n = 4
**Output:** 2
**Explanation:** There are two distinct solutions to the 4-queens puzzle as shown.


<strong class="example">Example 2:**



**Input:** n = 1
**Output:** 1


 

**Constraints:**



	- `1 <= n <= 9`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int ans=0;
    void solve(int row,int n,vector<int>& col,vector<int>& d1,vector<int>& d2){
        if(row==n){
            ans++;
            return;
        }
        for(int c=0;c<n;c++){
            if(col[c] || d1[row-c+n-1] || d2[row+c]) continue;
            col[c]=d1[row-c+n-1]=d2[row+c]=1;
            solve(row+1,n,col,d1,d2);
            col[c]=d1[row-c+n-1]=d2[row+c]=0;
        }
    }
    int totalNQueens(int n) {
        vector<int> col(n,0),d1(2*n-1,0),d2(2*n-1,0);
        solve(0,n,col,d1,d2);
        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
4
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Backtracking** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying backtracking to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
