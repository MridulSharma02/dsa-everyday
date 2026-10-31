<div align="center">

# 📦 3514. Number of Unique XOR Triplets II

*Pushed on October 31, 2026 · Problem #146 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 52.7%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Math` `Bit Manipulation` `Enumeration`

---

## 🧩 Problem Description

<p data-end="261" data-start="147">You are given an integer array `nums`.


A **XOR triplet** is defined as the XOR of three elements `nums[i] XOR nums[j] XOR nums[k]` where `i <= j <= k`.


Return the number of **unique** XOR triplet values from all possible triplets `(i, j, k)`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">nums = [1,3]</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


<p data-end="158" data-start="101">The possible XOR triplet values are:


<ul data-end="280" data-start="159">
	<li data-end="188" data-start="159">`(0, 0, 0) &rarr; 1 XOR 1 XOR 1 = 1`
	<li data-end="218" data-start="189">`(0, 0, 1) &rarr; 1 XOR 1 XOR 3 = 3`
	<li data-end="248" data-start="219">`(0, 1, 1) &rarr; 1 XOR 3 XOR 3 = 1`
	<li data-end="280" data-start="249">`(1, 1, 1) &rarr; 3 XOR 3 XOR 3 = 3`


<p data-end="343" data-start="282">The unique XOR values are <code data-end="316" data-start="308">{1, 3}`. Thus, the output is 2.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">nums = [6,7,8,9]</span>


**Output:** <span class="example-io">4</span>


**Explanation:**


The possible XOR triplet values are <code data-end="275" data-start="267">{6, 7, 8, 9}`. Thus, the output is 4.

</div>

 

**Constraints:**



	- `1 <= nums.length <= 1500`
	- `1 <= nums[i] <= 1500`

---

## 🪄 Hints
> 💡 What is the maximum possible XOR value achievable by any triplet?
> 💡 Let the maximum possible XOR value be stored in <code>max_xor</code>.

## 💻 My Solution

```cpp
class Solution {
public:
    int uniqueXorTriplets(vector<int>& nums) {
        const int MAXX = 2048;

        vector<bool> pairXor(MAXX, false);
        vector<bool> ans(MAXX, false);

        int n = nums.size();

        // All XORs of two elements (i <= j)
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                pairXor[nums[i] ^ nums[j]] = true;
            }
        }

        // XOR with third element
        for (int x = 0; x < MAXX; x++) {
            if (!pairXor[x]) continue;

            for (int v : nums)
                ans[x ^ v] = true;
        }

        int res = 0;
        for (bool x : ans)
            res += x;

        return res;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,3]
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
