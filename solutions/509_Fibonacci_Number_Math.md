<div align="center">

# 🔢 509. Fibonacci Number

*Pushed on July 15, 2026 · Problem #38 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 74.4%              |
| **Language**         | 🔠 Python         |

**Tags:** `Math` `Dynamic Programming` `Recursion` `Memoization`

---

## 🧩 Problem Description

The <b>Fibonacci numbers</b>, commonly denoted `F(n)` form a sequence, called the <b>Fibonacci sequence</b>, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,



F(0) = 0, F(1) = 1
F(n) = F(n - 1) + F(n - 2), for n > 1.


Given `n`, calculate `F(n)`.


 

<strong class="example">Example 1:**



**Input:** n = 2
**Output:** 1
**Explanation:** F(2) = F(1) + F(0) = 1 + 0 = 1.


<strong class="example">Example 2:**



**Input:** n = 3
**Output:** 2
**Explanation:** F(3) = F(2) + F(1) = 1 + 1 = 2.


<strong class="example">Example 3:**



**Input:** n = 4
**Output:** 3
**Explanation:** F(4) = F(3) + F(2) = 2 + 1 = 3.


 

**Constraints:**



	- `0 <= n <= 30`

---

## 💻 My Solution

```python
class Solution(object):
    def fib(self, n):
        """
        :type n: int
        :rtype: int
        """
        if n <= 1:
            return n
        return self.fib(n-1) + self.fib(n-2)

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
