<div align="center">

# 🌊 841. Keys and Rooms

*Pushed on August 30, 2026 · Problem #84 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌊 Depth-First Search   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 76.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Depth-First Search` `Breadth-First Search` `Graph Theory`

---

## 🧩 Problem Description

There are `n` rooms labeled from `0` to `n - 1` and all the rooms are locked except for room `0`. Your goal is to visit all the rooms. However, you cannot enter a locked room without having its key.


When you visit a room, you may find a set of **distinct keys** in it. Each key has a number on it, denoting which room it unlocks, and you can take all of them with you to unlock the other rooms.


Given an array `rooms` where `rooms[i]` is the set of keys that you can obtain if you visited room `i`, return `true` *if you can visit **all** the rooms, or* `false` *otherwise*.


 

<strong class="example">Example 1:**



**Input:** rooms = [[1],[2],[3],[]]
**Output:** true
**Explanation:** 
We visit room 0 and pick up key 1.
We then visit room 1 and pick up key 2.
We then visit room 2 and pick up key 3.
We then visit room 3.
Since we were able to visit every room, we return true.


<strong class="example">Example 2:**



**Input:** rooms = [[1,3],[3,0,1],[2],[0]]
**Output:** false
**Explanation:** We can not enter room number 2 since the only key that unlocks it is in that room.


 

**Constraints:**



	- `n == rooms.length`
	- `2 <= n <= 1000`
	- `0 <= rooms[i].length <= 1000`
	- `1 <= sum(rooms[i].length) <= 3000`
	- `0 <= rooms[i][j] < n`
	- All the values of `rooms[i]` are **unique**.

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool canVisitAllRooms(vector<vector<int>>& rooms) {
        int n = rooms.size();
        vector<bool> visited(n, false);
        stack<int> st;

        st.push(0);
        visited[0] = true;

        while (!st.empty()) {
            int room = st.top();
            st.pop();

            for (int key : rooms[room]) {
                if (!visited[key]) {
                    visited[key] = true;
                    st.push(key);
                }
            }
        }

        for (bool v : visited) {
            if (!v) return false;
        }

        return true;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1],[2],[3],[]]
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
