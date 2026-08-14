<div align="center">

# 🔢 3658. GCD of Odd and Even Sums

*Pushed on August 14, 2026 · Problem #68 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 89.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `Number Theory`

---

## 🧩 Problem Description

You are given an integer `n`. Your task is to compute the **GCD** (greatest common divisor) of two values:



	- 
	`sumOdd`: the sum of the smallest `n` positive odd numbers.

	
	- 
	`sumEven`: the sum of the smallest `n` positive even numbers.

	


Return the GCD of `sumOdd` and `sumEven`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">n = 4</span>


**Output:** <span class="example-io">4</span>


**Explanation:**



	- Sum of the first 4 odd numbers `sumOdd = 1 + 3 + 5 + 7 = 16`
	- Sum of the first 4 even numbers `sumEven = 2 + 4 + 6 + 8 = 20`


Hence, `GCD(sumOdd, sumEven) = GCD(16, 20) = 4`.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">n = 5</span>


**Output:** <span class="example-io">5</span>


**Explanation:**



	- Sum of the first 5 odd numbers `sumOdd = 1 + 3 + 5 + 7 + 9 = 25`
	- Sum of the first 5 even numbers `sumEven = 2 + 4 + 6 + 8 + 10 = 30`


Hence, `GCD(sumOdd, sumEven) = GCD(25, 30) = 5`.

</div>

 

**Constraints:**



	- `1 <= n <= 10​​​​​​​00`

---

## 🪄 Hints
> 💡 The first <code>n</code> odd numbers sum to <code>n * n</code>
> 💡 First <code>n</code> even numbers sum to <code>n * (n + 1)</code>

## 💻 My Solution

```cpp
class Solution {
public:
    int gcdOfOddEvenSums(int n) {
        return n;
    }
};

```

---

## 🧪 Sample Test Case

```
4
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
