<div align="center">

# 🌊 547. Number of Provinces

*Pushed on October 27, 2026 · Problem #142 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌊 Depth-First Search   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 71.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Depth-First Search` `Breadth-First Search` `Union-Find` `Graph Theory`

---

## 🧩 Problem Description

There are `n` cities. Some of them are connected, while some are not. If city `a` is connected directly with city `b`, and city `b` is connected directly with city `c`, then city `a` is connected indirectly with city `c`.


A **province** is a group of directly or indirectly connected cities and no other cities outside of the group.


You are given an `n x n` matrix `isConnected` where `isConnected[i][j] = 1` if the `i^th` city and the `j^th` city are directly connected, and `isConnected[i][j] = 0` otherwise.


Return *the total number of **provinces***.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/12/24/graph1.jpg" style="width: 222px; height: 142px;" />

**Input:** isConnected = [[1,1,0],[1,1,0],[0,0,1]]
**Output:** 2


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/12/24/graph2.jpg" style="width: 222px; height: 142px;" />

**Input:** isConnected = [[1,0,0],[0,1,0],[0,0,1]]
**Output:** 3


 

**Constraints:**



	- `1 <= n <= 200`
	- `n == isConnected.length`
	- `n == isConnected[i].length`
	- `isConnected[i][j]` is `1` or `0`.
	- `isConnected[i][i] == 1`
	- `isConnected[i][j] == isConnected[j][i]`

---

## 💻 My Solution

```cpp
class Solution {
public:
    void dfs(int city, vector<vector<int>>& isConnected, vector<int>& vis) {
        vis[city] = 1;

        for (int nei = 0; nei < isConnected.size(); nei++) {
            if (isConnected[city][nei] == 1 && !vis[nei]) {
                dfs(nei, isConnected, vis);
            }
        }
    }

    int findCircleNum(vector<vector<int>>& isConnected) {
        int n = isConnected.size();
        vector<int> vis(n, 0);
        int provinces = 0;

        for (int i = 0; i < n; i++) {
            if (!vis[i]) {
                provinces++;
                dfs(i, isConnected, vis);
            }
        }

        return provinces;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1,1,0],[1,1,0],[0,0,1]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Depth-First Search** techniques.
> The key insight is to leverage `O(V + E)` time complexity
> by applying depth-first search to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
