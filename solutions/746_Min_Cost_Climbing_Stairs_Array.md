<div align="center">

# 📦 746. Min Cost Climbing Stairs

*Pushed on October 01, 2026 · Problem #116 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 68.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Dynamic Programming`

---

## 🧩 Problem Description

You are given an integer array `cost` where `cost[i]` is the cost of `i^th` step on a staircase.


Once you pay the cost, you can either climb **one** or **two** steps.


You can either start from the step with index 0, or the step with index 1.


Return the **minimum** cost to reach the top of the staircase, which is the position just past the last step (index `cost.length`).


 

<strong class="example">Example 1:**



**Input:** cost = [10,<u>15</u>,20]
**Output:** 15
**Explanation:** You will start at index 1.
- Pay 15 and climb two steps to reach the top.
The total cost is 15.


<strong class="example">Example 2:**



**Input:** cost = [<u>1</u>,100,<u>1</u>,1,<u>1</u>,100,<u>1</u>,<u>1</u>,100,<u>1</u>]
**Output:** 6
**Explanation:** You will start at index 0.
- Pay 1 and climb two steps to reach index 2.
- Pay 1 and climb two steps to reach index 4.
- Pay 1 and climb two steps to reach index 6.
- Pay 1 and climb one step to reach index 7.
- Pay 1 and climb two steps to reach index 9.
- Pay 1 and climb one step to reach the top.
The total cost is 6.


 

**Constraints:**



	- `2 <= cost.length <= 1000`
	- `0 <= cost[i] <= 999`

---

## 🪄 Hints
> 💡 Build an array dp where dp[i] is the minimum cost to climb to the top starting from the ith staircase.
> 💡 Assuming we have n staircase labeled from 0 to n - 1 and assuming the top is n, then dp[n] = 0, marking that if you are at the top, the cost is 0.

## 💻 My Solution

```cpp
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int a = 0, b = 0;

        for (int i = 2; i <= cost.size(); i++) {
            int curr = min(b + cost[i - 1], a + cost[i - 2]);
            a = b;
            b = curr;
        }

        return b;
    }
};

```

---

## 🧪 Sample Test Case

```
[10,15,20]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
