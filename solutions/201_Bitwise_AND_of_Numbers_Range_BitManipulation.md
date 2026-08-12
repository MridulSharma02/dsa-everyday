<div align="center">

# ⚡ 201. Bitwise AND of Numbers Range

*Pushed on August 12, 2026 · Problem #66 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | ⚡ Bit Manipulation   |
| **Time Complexity**  | ⏱️ `O(1)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 49.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Bit Manipulation`

---

## 🧩 Problem Description

Given two integers `left` and `right` that represent the range `[left, right]`, return *the bitwise AND of all numbers in this range, inclusive*.


 

<strong class="example">Example 1:**



**Input:** left = 5, right = 7
**Output:** 4


<strong class="example">Example 2:**



**Input:** left = 0, right = 0
**Output:** 0


<strong class="example">Example 3:**



**Input:** left = 1, right = 2147483647
**Output:** 0


 

**Constraints:**



	- `0 <= left <= right <= 2^31 - 1`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int rangeBitwiseAnd(int left, int right) {
        int count=0;
        while(left!=right){
            left>>=1;
            right>>=1;
            count++;
        }

        return left<<count;
    }
};

```

---

## 🧪 Sample Test Case

```
5
7
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Bit Manipulation** techniques.
> The key insight is to leverage `O(1)` time complexity
> by applying bit manipulation to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
