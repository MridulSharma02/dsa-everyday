<div align="center">

# 🔢 89. Gray Code

*Pushed on August 15, 2026 · Problem #69 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 65.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `Backtracking` `Bit Manipulation`

---

## 🧩 Problem Description

An **n-bit gray code sequence** is a sequence of `2^n` integers where:



	- Every integer is in the **inclusive** range `[0, 2^n - 1]`,
	- The first integer is `0`,
	- An integer appears **no more than once** in the sequence,
	- The binary representation of every pair of **adjacent** integers differs by **exactly one bit**, and
	- The binary representation of the **first** and **last** integers differs by **exactly one bit**.


Given an integer `n`, return *any valid **n-bit gray code sequence***.


 

<strong class="example">Example 1:**



**Input:** n = 2
**Output:** [0,1,3,2]
**Explanation:**
The binary representation of [0,1,3,2] is [00,01,11,10].
- 0<u>0</u> and 0<u>1</u> differ by one bit
- <u>0</u>1 and <u>1</u>1 differ by one bit
- 1<u>1</u> and 1<u>0</u> differ by one bit
- <u>1</u>0 and <u>0</u>0 differ by one bit
[0,2,3,1] is also a valid gray code sequence, whose binary representation is [00,10,11,01].
- <u>0</u>0 and <u>1</u>0 differ by one bit
- 1<u>0</u> and 1<u>1</u> differ by one bit
- <u>1</u>1 and <u>0</u>1 differ by one bit
- 0<u>1</u> and 0<u>0</u> differ by one bit


<strong class="example">Example 2:**



**Input:** n = 1
**Output:** [0,1]


 

**Constraints:**



	- `1 <= n <= 16`

---

## 💻 My Solution

```cpp
class Solution {
public:
    vector<int> grayCode(int n) {
        vector<int> ans;

        for(int i=0;i<(1<<n);i++)
            ans.push_back(i^(i>>1));

        return ans;
    }
};

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
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
