<div align="center">

# 📦 1926. Nearest Exit from Entrance in Maze

*Pushed on October 13, 2026 · Problem #127 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 49.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Breadth-First Search` `Matrix`

---

## 🧩 Problem Description

You are given an `m x n` matrix `maze` (**0-indexed**) with empty cells (represented as `&#39;.&#39;`) and walls (represented as `&#39;+&#39;`). You are also given the `entrance` of the maze, where `entrance = [entrancerow, entrancecol]` denotes the row and column of the cell you are initially standing at.


In one step, you can move one cell **up**, **down**, **left**, or **right**. You cannot step into a cell with a wall, and you cannot step outside the maze. Your goal is to find the **nearest exit** from the `entrance`. An **exit** is defined as an **empty cell** that is at the **border** of the `maze`. The `entrance` **does not count** as an exit.


Return *the **number of steps** in the shortest path from the *`entrance`* to the nearest exit, or *`-1`* if no such path exists*.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/06/04/nearest1-grid.jpg" style="width: 333px; height: 253px;" />

**Input:** maze = [[&quot;+&quot;,&quot;+&quot;,&quot;.&quot;,&quot;+&quot;],[&quot;.&quot;,&quot;.&quot;,&quot;.&quot;,&quot;+&quot;],[&quot;+&quot;,&quot;+&quot;,&quot;+&quot;,&quot;.&quot;]], entrance = [1,2]
**Output:** 1
**Explanation:** There are 3 exits in this maze at [1,0], [0,2], and [2,3].
Initially, you are at the entrance cell [1,2].
- You can reach [1,0] by moving 2 steps left.
- You can reach [0,2] by moving 1 step up.
It is impossible to reach [2,3] from the entrance.
Thus, the nearest exit is [0,2], which is 1 step away.


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/06/04/nearesr2-grid.jpg" style="width: 253px; height: 253px;" />

**Input:** maze = [[&quot;+&quot;,&quot;+&quot;,&quot;+&quot;],[&quot;.&quot;,&quot;.&quot;,&quot;.&quot;],[&quot;+&quot;,&quot;+&quot;,&quot;+&quot;]], entrance = [1,0]
**Output:** 2
**Explanation:** There is 1 exit in this maze at [1,2].
[1,0] does not count as an exit since it is the entrance cell.
Initially, you are at the entrance cell [1,0].
- You can reach [1,2] by moving 2 steps right.
Thus, the nearest exit is [1,2], which is 2 steps away.


<strong class="example">Example 3:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/06/04/nearest3-grid.jpg" style="width: 173px; height: 93px;" />

**Input:** maze = [[&quot;.&quot;,&quot;+&quot;]], entrance = [0,0]
**Output:** -1
**Explanation:** There are no exits in this maze.


 

**Constraints:**



	- `maze.length == m`
	- `maze[i].length == n`
	- `1 <= m, n <= 100`
	- `maze[i][j]` is either `&#39;.&#39;` or `&#39;+&#39;`.
	- `entrance.length == 2`
	- `0 <= entrancerow < m`
	- `0 <= entrancecol < n`
	- `entrance` will always be an empty cell.

---

## 🪄 Hints
> 💡 Which type of traversal lets you find the distance from a point?
> 💡 Try using a Breadth First Search.

## 💻 My Solution

```cpp
class Solution {
public:
    int nearestExit(vector<vector<char>>& maze, vector<int>& entrance) {
        int m = maze.size(), n = maze[0].size();

        queue<pair<int,int>> q;
        q.push({entrance[0], entrance[1]});

        vector<vector<int>> vis(m, vector<int>(n, 0));
        vis[entrance[0]][entrance[1]] = 1;

        int steps = 0;
        int dir[4][2] = {{1,0},{-1,0},{0,1},{0,-1}};

        while (!q.empty()) {
            int sz = q.size();

            while (sz--) {
                auto [r, c] = q.front();
                q.pop();

                if ((r == 0 || r == m - 1 || c == 0 || c == n - 1) &&
                    !(r == entrance[0] && c == entrance[1]))
                    return steps;

                for (auto& d : dir) {
                    int nr = r + d[0];
                    int nc = c + d[1];

                    if (nr >= 0 && nr < m && nc >= 0 && nc < n &&
                        maze[nr][nc] == '.' && !vis[nr][nc]) {
                        vis[nr][nc] = 1;
                        q.push({nr, nc});
                    }
                }
            }

            steps++;
        }

        return -1;
    }
};

```

---

## 🧪 Sample Test Case

```
[["+","+",".","+"],[".",".",".","+"],["+","+","+","."]]
[1,2]
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
