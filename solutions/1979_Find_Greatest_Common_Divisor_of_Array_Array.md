<div align="center">

# 📦 1979. Find Greatest Common Divisor of Array

*Pushed on July 31, 2026 · Problem #54 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 83.5%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Math` `Number Theory`

---

## 🧩 Problem Description

Given an integer array `nums`, return** ***the **greatest common divisor** of the smallest number and largest number in *`nums`.


The **greatest common divisor** of two numbers is the largest positive integer that evenly divides both numbers.


 

<strong class="example">Example 1:**



**Input:** nums = [2,5,6,9,10]
**Output:** 2
**Explanation:**
The smallest number in nums is 2.
The largest number in nums is 10.
The greatest common divisor of 2 and 10 is 2.


<strong class="example">Example 2:**



**Input:** nums = [7,5,6,8,3]
**Output:** 1
**Explanation:**
The smallest number in nums is 3.
The largest number in nums is 8.
The greatest common divisor of 3 and 8 is 1.


<strong class="example">Example 3:**



**Input:** nums = [3,3]
**Output:** 3
**Explanation:**
The smallest number in nums is 3.
The largest number in nums is 3.
The greatest common divisor of 3 and 3 is 3.


 

**Constraints:**



	- `2 <= nums.length <= 1000`
	- `1 <= nums[i] <= 1000`

---

## 🪄 Hints
> 💡 Find the minimum and maximum in one iteration. Let them be mn and mx.
> 💡 Try all the numbers in the range [1, mn] and check the largest number which divides both of them.

## 💻 My Solution

```cpp
class Solution {
public:
    int findGCD(vector<int>& nums) {
        int mn=*min_element(nums.begin(),nums.end());
        int mx=*max_element(nums.begin(),nums.end());

        return gcd(mn,mx);
    }
};

```

---

## 🧪 Sample Test Case

```
[2,5,6,9,10]
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
