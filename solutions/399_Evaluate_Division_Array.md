<div align="center">

# 📦 399. Evaluate Division

*Pushed on July 13, 2026 · Problem #36 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.4%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `String` `Depth-First Search` `Breadth-First Search` `Union-Find` `Graph Theory` `Shortest Path`

---

## 🧩 Problem Description

You are given an array of variable pairs `equations` and an array of real numbers `values`, where `equations[i] = [Ai, Bi]` and `values[i]` represent the equation `Ai / Bi = values[i]`. Each `Ai` or `Bi` is a string that represents a single variable.


You are also given some `queries`, where `queries[j] = [Cj, Dj]` represents the `j^th` query where you must find the answer for `Cj / Dj = ?`.


Return *the answers to all queries*. If a single answer cannot be determined, return `-1.0`.


**Note:** The input is always valid. You may assume that evaluating the queries will not result in division by zero and that there is no contradiction.


**Note: **The variables that do not occur in the list of equations are undefined, so the answer cannot be determined for them.


 

<strong class="example">Example 1:**



**Input:** equations = [[&quot;a&quot;,&quot;b&quot;],[&quot;b&quot;,&quot;c&quot;]], values = [2.0,3.0], queries = [[&quot;a&quot;,&quot;c&quot;],[&quot;b&quot;,&quot;a&quot;],[&quot;a&quot;,&quot;e&quot;],[&quot;a&quot;,&quot;a&quot;],[&quot;x&quot;,&quot;x&quot;]]
**Output:** [6.00000,0.50000,-1.00000,1.00000,-1.00000]
**Explanation:** 
Given: *a / b = 2.0*, *b / c = 3.0*
queries are: *a / c = ?*, *b / a = ?*, *a / e = ?*, *a / a = ?*, *x / x = ? *
return: [6.0, 0.5, -1.0, 1.0, -1.0 ]
note: x is undefined => -1.0

<strong class="example">Example 2:**



**Input:** equations = [[&quot;a&quot;,&quot;b&quot;],[&quot;b&quot;,&quot;c&quot;],[&quot;bc&quot;,&quot;cd&quot;]], values = [1.5,2.5,5.0], queries = [[&quot;a&quot;,&quot;c&quot;],[&quot;c&quot;,&quot;b&quot;],[&quot;bc&quot;,&quot;cd&quot;],[&quot;cd&quot;,&quot;bc&quot;]]
**Output:** [3.75000,0.40000,5.00000,0.20000]


<strong class="example">Example 3:**



**Input:** equations = [[&quot;a&quot;,&quot;b&quot;]], values = [0.5], queries = [[&quot;a&quot;,&quot;b&quot;],[&quot;b&quot;,&quot;a&quot;],[&quot;a&quot;,&quot;c&quot;],[&quot;x&quot;,&quot;y&quot;]]
**Output:** [0.50000,2.00000,-1.00000,-1.00000]


 

**Constraints:**



	- `1 <= equations.length <= 20`
	- `equations[i].length == 2`
	- `1 <= Ai.length, Bi.length <= 5`
	- `values.length == equations.length`
	- `0.0 < values[i] <= 20.0`
	- `1 <= queries.length <= 20`
	- `queries[i].length == 2`
	- `1 <= Cj.length, Dj.length <= 5`
	- `Ai, Bi, Cj, Dj` consist of lower case English letters and digits.

---

## 🪄 Hints
> 💡 Do you recognize this as a graph problem?

## 💻 My Solution

```cpp
class Solution {
public:
    double dfs(string src, string dst,
               unordered_map<string, vector<pair<string, double>>>& graph,
               unordered_set<string>& vis,
               double product) {
        
        if (src == dst) return product;

        vis.insert(src);

        for (auto& [nei, val] : graph[src]) {
            if (!vis.count(nei)) {
                double res = dfs(nei, dst, graph, vis, product * val);
                if (res != -1.0) return res;
            }
        }

        return -1.0;
    }

    vector<double> calcEquation(vector<vector<string>>& equations,
                                vector<double>& values,
                                vector<vector<string>>& queries) {

        unordered_map<string, vector<pair<string, double>>> graph;

        for (int i = 0; i < equations.size(); i++) {
            string a = equations[i][0];
            string b = equations[i][1];
            double v = values[i];

            graph[a].push_back({b, v});
            graph[b].push_back({a, 1.0 / v});
        }

        vector<double> ans;

        for (auto& q : queries) {
            string src = q[0];
            string dst = q[1];

            if (!graph.count(src) || !graph.count(dst)) {
                ans.push_back(-1.0);
                continue;
            }

            unordered_set<string> vis;
            ans.push_back(dfs(src, dst, graph, vis, 1.0));
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[["a","b"],["b","c"]]
[2.0,3.0]
[["a","c"],["b","a"],["a","e"],["a","a"],["x","x"]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(V + E)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
