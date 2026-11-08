<div align="center">

# 🔢 231. Power of Two

*Pushed on November 08, 2026 · Problem #154 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 50.7%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `Bit Manipulation` `Recursion`

---

## 🧩 Problem Description

Given an integer `n`, return *`true` if it is a power of two. Otherwise, return `false`*.


An integer `n` is a power of two, if there exists an integer `x` such that `n == 2^x`.


 

<strong class="example">Example 1:**



**Input:** n = 1
**Output:** true
**Explanation: **2^0 = 1


<strong class="example">Example 2:**



**Input:** n = 16
**Output:** true
**Explanation: **2^4 = 16


<strong class="example">Example 3:**



**Input:** n = 3
**Output:** false


 

**Constraints:**



	- `-2^31 <= n <= 2^31 - 1`


 

**Follow up:** Could you solve it without loops/recursion?

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n<=0) return false;

        return (n & (n-1)) == 0;
    }
};

```

---

## 🧪 Sample Test Case

```
1
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Math** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying math to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
