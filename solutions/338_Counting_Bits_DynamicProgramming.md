<div align="center">

# 🧬 338. Counting Bits

*Pushed on June 25, 2026 · Problem #18 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🧬 Dynamic Programming   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 80.7%              |
| **Language**         | 🔠 Python         |

**Tags:** `Dynamic Programming` `Bit Manipulation`

---

## 🧩 Problem Description

Given an integer `n`, return *an array *`ans`* of length *`n + 1`* such that for each *`i`* *(`0 <= i <= n`)*, *`ans[i]`* is the **number of ***`1`***&#39;s** in the binary representation of *`i`.


 

<strong class="example">Example 1:**



**Input:** n = 2
**Output:** [0,1,1]
**Explanation:**
0 --> 0
1 --> 1
2 --> 10


<strong class="example">Example 2:**



**Input:** n = 5
**Output:** [0,1,1,2,1,2]
**Explanation:**
0 --> 0
1 --> 1
2 --> 10
3 --> 11
4 --> 100
5 --> 101


 

**Constraints:**



	- `0 <= n <= 10^5`


 

**Follow up:**



	- It is very easy to come up with a solution with a runtime of `O(n log n)`. Can you do it in linear time `O(n)` and possibly in a single pass?
	- Can you do it without using any built-in function (i.e., like `__builtin_popcount` in C++)?

---

## 🪄 Hints
> 💡 You should make use of what you have produced already.
> 💡 Divide the numbers in ranges like [2-3], [4-7], [8-15] and so on. And try to generate new range from previous.

## 💻 My Solution

```python
class Solution(object):
    def countBits(self, n):
        """
        :type n: int
        :rtype: List[int]
        """
        ans = [0] * (n + 1)

        for i in range(1, n + 1):
            ans[i] = ans[i // 2] + (i % 2)

        return ans

```

---

## 🧪 Sample Test Case

```
2
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Dynamic Programming** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying dynamic programming to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
