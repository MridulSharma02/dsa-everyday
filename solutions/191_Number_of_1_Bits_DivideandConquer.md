<div align="center">

# 💻 191. Number of 1 Bits

*Pushed on October 26, 2026 · Problem #141 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 💻 Divide and Conquer   |
| **Time Complexity**  | ⏱️ `O(1)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 77.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Divide and Conquer` `Bit Manipulation`

---

## 🧩 Problem Description

Given a positive integer `n`, write a function that returns the number of <span data-keyword="set-bit">set bits</span> in its binary representation (also known as the <a href="http://en.wikipedia.org/wiki/Hamming_weight" target="_blank">Hamming weight</a>).


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">n = 11</span>


**Output:** <span class="example-io">3</span>


**Explanation:**


The input binary string **1011** has a total of three set bits.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">n = 128</span>


**Output:** <span class="example-io">1</span>


**Explanation:**


The input binary string **10000000** has a total of one set bit.

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">n = 2147483645</span>


**Output:** <span class="example-io">30</span>


**Explanation:**


The input binary string **1111111111111111111111111111101** has a total of thirty set bits.

</div>

 

**Constraints:**



	- `1 <= n <= 2^31 - 1`


 

**Follow up:** If this function is called many times, how would you optimize it?

---

## 💻 My Solution

```cpp
class Solution {
public:
    int hammingWeight(int n){
        int count=0;
        while(n){
            count+=(n&1);
            n>>=1;
        }

        return count;
    }
};

```

---

## 🧪 Sample Test Case

```
11
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Divide and Conquer** techniques.
> The key insight is to leverage `O(1)` time complexity
> by applying divide and conquer to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
