<div align="center">

# 📦 304. Range Sum Query 2D - Immutable

*Pushed on November 21, 2026 · Problem #166 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 59.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Design` `Matrix` `Prefix Sum`

---

## 🧩 Problem Description

Given a 2D matrix `matrix`, handle multiple queries of the following type:



	- Calculate the **sum** of the elements of `matrix` inside the rectangle defined by its **upper left corner** `(row1, col1)` and **lower right corner** `(row2, col2)`.


Implement the `NumMatrix` class:



	- `NumMatrix(int[][] matrix)` Initializes the object with the integer matrix `matrix`.
	- `int sumRegion(int row1, int col1, int row2, int col2)` Returns the **sum** of the elements of `matrix` inside the rectangle defined by its **upper left corner** `(row1, col1)` and **lower right corner** `(row2, col2)`.


You must design an algorithm where `sumRegion` works on `O(1)` time complexity.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/03/14/sum-grid.jpg" style="width: 415px; height: 415px;" />

**Input**
[&quot;NumMatrix&quot;, &quot;sumRegion&quot;, &quot;sumRegion&quot;, &quot;sumRegion&quot;]
[[[[3, 0, 1, 4, 2], [5, 6, 3, 2, 1], [1, 2, 0, 1, 5], [4, 1, 0, 1, 7], [1, 0, 3, 0, 5]]], [2, 1, 4, 3], [1, 1, 2, 2], [1, 2, 2, 4]]
**Output**
[null, 8, 11, 12]

**Explanation**
NumMatrix numMatrix = new NumMatrix([[3, 0, 1, 4, 2], [5, 6, 3, 2, 1], [1, 2, 0, 1, 5], [4, 1, 0, 1, 7], [1, 0, 3, 0, 5]]);
numMatrix.sumRegion(2, 1, 4, 3); // return 8 (i.e sum of the red rectangle)
numMatrix.sumRegion(1, 1, 2, 2); // return 11 (i.e sum of the green rectangle)
numMatrix.sumRegion(1, 2, 2, 4); // return 12 (i.e sum of the blue rectangle)


 

**Constraints:**



	- `m == matrix.length`
	- `n == matrix[i].length`
	- `1 <= m, n <= 200`
	- `-10^4 <= matrix[i][j] <= 10^4`
	- `0 <= row1 <= row2 < m`
	- `0 <= col1 <= col2 < n`
	- At most `10^4` calls will be made to `sumRegion`.

---

## 💻 My Solution

```cpp
class NumMatrix {
public:
    vector<vector<int>> prefix;
    NumMatrix(vector<vector<int>>& matrix) {

        int m=matrix.size();
        int n=matrix[0].size();
        prefix = matrix;

        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                if(i>0)
                    prefix[i][j]+=prefix[i-1][j];
                if(j>0)
                    prefix[i][j]+=prefix[i][j-1];
                if(i>0 && j>0)
                    prefix[i][j]-=prefix[i-1][j-1];
            }
        }
    }

    int sumRegion(int row1, int col1, int row2, int col2) {
        int sum=prefix[row2][col2];
        if(row1>0)
            sum-=prefix[row1-1][col2];
        if(col1>0)
            sum-=prefix[row2][col1-1];
        if(row1>0 && col1>0)
            sum+=prefix[row1-1][col1-1];

        return sum;
    }
};

/**
 * Your NumMatrix object will be instantiated and called as such:
 * NumMatrix* obj = new NumMatrix(matrix);
 * int param_1 = obj->sumRegion(row1,col1,row2,col2);
 */

```

---

## 🧪 Sample Test Case

```
["NumMatrix","sumRegion","sumRegion","sumRegion"]
[[[[3,0,1,4,2],[5,6,3,2,1],[1,2,0,1,5],[4,1,0,1,7],[1,0,3,0,5]]],[2,1,4,3],[1,1,2,2],[1,2,2,4]]
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
