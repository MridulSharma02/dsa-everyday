<div align="center">

# 📦 3513. Number of Unique XOR Triplets I

*Pushed on October 30, 2026 · Problem #145 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 57.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Math` `Bit Manipulation`

---

## 🧩 Problem Description

You are given an integer array `nums` of length `n`, where `nums` is a **<span data-keyword="permutation">permutation</span>** of the numbers in the range `[1, n]`.


A **XOR triplet** is defined as the XOR of three elements `nums[i] XOR nums[j] XOR nums[k]` where `i <= j <= k`.


Return the number of **unique** XOR triplet values from all possible triplets `(i, j, k)`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">nums = [1,2]</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


The possible XOR triplet values are:



	- `(0, 0, 0) &rarr; 1 XOR 1 XOR 1 = 1`
	- `(0, 0, 1) &rarr; 1 XOR 1 XOR 2 = 2`
	- `(0, 1, 1) &rarr; 1 XOR 2 XOR 2 = 1`
	- `(1, 1, 1) &rarr; 2 XOR 2 XOR 2 = 2`


The unique XOR values are `{1, 2}`, so the output is 2.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">nums = [3,1,2]</span>


**Output:** <span class="example-io">4</span>


**Explanation:**


The possible XOR triplet values include:



	- `(0, 0, 0) &rarr; 3 XOR 3 XOR 3 = 3`
	- `(0, 0, 1) &rarr; 3 XOR 3 XOR 1 = 1`
	- `(0, 0, 2) &rarr; 3 XOR 3 XOR 2 = 2`
	- `(0, 1, 2) &rarr; 3 XOR 1 XOR 2 = 0`


The unique XOR values are `{0, 1, 2, 3}`, so the output is 4.

</div>

 

**Constraints:**



	- `1 <= n == nums.length <= 10^5`
	- `1 <= nums[i] <= n`
	- `nums` is a permutation of integers from `1` to `n`.

---

## 🪄 Hints
> 💡 What is the maximum and minimum value we can obtain using the given numbers?
> 💡 Can we generate all numbers within that range?

## 💻 My Solution

```cpp
class Solution {
public:
    int uniqueXorTriplets(vector<int>& nums) {
        int n=nums.size();
        if (n==1) return 1;
        if (n==2) return 2;

        int ans=1;
        while (ans<=n)
            ans<<=1;

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
