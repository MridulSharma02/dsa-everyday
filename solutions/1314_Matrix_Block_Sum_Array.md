<div align="center">

# 📦 1314. Matrix Block Sum

*Pushed on October 23, 2026 · Problem #138 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 77.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Matrix` `Prefix Sum`

---

## 🧩 Problem Description

Given a `m x n` matrix `mat` and an integer `k`, return *a matrix* `answer` *where each* `answer[i][j]` *is the sum of all elements* `mat[r][c]` *for*:



	- `i - k <= r <= i + k,`
	- `j - k <= c <= j + k`, and
	- `(r, c)` is a valid position in the matrix.


 

<strong class="example">Example 1:**



**Input:** mat = [[1,2,3],[4,5,6],[7,8,9]], k = 1
**Output:** [[12,21,16],[27,45,33],[24,39,28]]


<strong class="example">Example 2:**



**Input:** mat = [[1,2,3],[4,5,6],[7,8,9]], k = 2
**Output:** [[45,45,45],[45,45,45],[45,45,45]]


 

**Constraints:**



	- `m == mat.length`
	- `n == mat[i].length`
	- `1 <= m, n, k <= 100`
	- `1 <= mat[i][j] <= 100`

---

## 🪄 Hints
> 💡 How to calculate the required sum for a cell (i,j) fast ?
> 💡 Use the concept of cumulative sum array.

## 💻 My Solution

```cpp
class Solution {
public:
    vector<vector<int>> matrixBlockSum(vector<vector<int>>& mat, int k) {
        int m=mat.size();
        int n=mat[0].size();
        vector<vector<int>> prefix=mat;
        
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

        vector<vector<int>> answer(m,vector<int>(n));

        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                int r1=max(i-k,0);
                int c1=max(j-k,0);
                int r2=min(i+k,m-1);
                int c2=min(j+k,n-1);

                answer[i][j]=prefix[r2][c2];
                if(r1>0)
                    answer[i][j]-=prefix[r1-1][c2];
                if(c1>0)
                    answer[i][j]-=prefix[r2][c1-1];
                if(r1>0 && c1>0)
                    answer[i][j]+=prefix[r1-1][c1-1];
            }
        }    
        return answer;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1,2,3],[4,5,6],[7,8,9]]
1
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
