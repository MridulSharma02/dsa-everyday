<div align="center">

# 🔢 70. Climbing Stairs

*Pushed on June 19, 2026 · Problem #12 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 54.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `Math` `Dynamic Programming` `Memoization`

---

## 🧩 Problem Description

You are climbing a staircase. It takes `n` steps to reach the top.


Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?


 

<strong class="example">Example 1:**



**Input:** n = 2
**Output:** 2
**Explanation:** There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps


<strong class="example">Example 2:**



**Input:** n = 3
**Output:** 3
**Explanation:** There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step


 

**Constraints:**



	- `1 <= n <= 45`

---

## 🪄 Hints
> 💡 To reach nth step, what could have been your previous steps? (Think about the step sizes)

## 💻 My Solution

```python
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        a, b = 1, 1  
        for _ in range(n):
            a, b = b, a + b
        return a
        

```

---

## 🧪 Sample Test Case

```
2
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Math** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying math to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
