<div align="center">

# 🌊 1466. Reorder Routes to Make All Paths Lead to the City Zero

*Pushed on November 28, 2026 · Problem #173 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌊 Depth-First Search   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 66.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Depth-First Search` `Breadth-First Search` `Graph Theory`

---

## 🧩 Problem Description

There are `n` cities numbered from `0` to `n - 1` and `n - 1` roads such that there is only one way to travel between two different cities (this network form a tree). Last year, The ministry of transport decided to orient the roads in one direction because they are too narrow.


Roads are represented by `connections` where `connections[i] = [ai, bi]` represents a road from city `ai` to city `bi`.


This year, there will be a big event in the capital (city `0`), and many people want to travel to this city.


Your task consists of reorienting some roads such that each city can visit the city `0`. Return the **minimum** number of edges changed.


It&#39;s **guaranteed** that each city can reach city `0` after reorder.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/05/13/sample_1_1819.png" style="width: 311px; height: 189px;" />

**Input:** n = 6, connections = [[0,1],[1,3],[2,3],[4,0],[4,5]]
**Output:** 3
**Explanation: **Change the direction of edges show in red such that each node can reach the node 0 (capital).


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/05/13/sample_2_1819.png" style="width: 509px; height: 79px;" />

**Input:** n = 5, connections = [[1,0],[1,2],[3,2],[3,4]]
**Output:** 2
**Explanation: **Change the direction of edges show in red such that each node can reach the node 0 (capital).


<strong class="example">Example 3:**



**Input:** n = 3, connections = [[1,0],[2,0]]
**Output:** 0


 

**Constraints:**



	- `2 <= n <= 5 * 10^4`
	- `connections.length == n - 1`
	- `connections[i].length == 2`
	- `0 <= ai, bi <= n - 1`
	- `ai != bi`

---

## 🪄 Hints
> 💡 Treat the graph as undirected. Start a dfs from the root, if you come across an edge in the forward direction, you need to reverse the edge.

## 💻 My Solution

```cpp
class Solution {
public:
    int changes = 0;

    void dfs(int node, int parent, vector<vector<pair<int,int>>>& adj) {
        for (auto& [nei, cost] : adj[node]) {
            if (nei == parent) continue;

            changes += cost;
            dfs(nei, node, adj);
        }
    }

    int minReorder(int n, vector<vector<int>>& connections) {
        vector<vector<pair<int,int>>> adj(n);

        for (auto& e : connections) {
            int a = e[0], b = e[1];

            adj[a].push_back({b, 1});
            adj[b].push_back({a, 0});
        }

        dfs(0, -1, adj);

        return changes;
    }
};

```

---

## 🧪 Sample Test Case

```
6
[[0,1],[1,3],[2,3],[4,0],[4,5]]
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
