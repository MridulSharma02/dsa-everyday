<div align="center">

# 📦 34. Find First and Last Position of Element in Sorted Array

*Pushed on July 30, 2026 · Problem #53 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 49.4%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Binary Search`

---

## 🧩 Problem Description

Given an array of integers `nums` sorted in non-decreasing order, find the starting and ending position of a given `target` value.


If `target` is not found in the array, return `[-1, -1]`.


You must write an algorithm with `O(log n)` runtime complexity.


 

<strong class="example">Example 1:**

**Input:** nums = [5,7,7,8,8,10], target = 8
**Output:** [3,4]
<strong class="example">Example 2:**

**Input:** nums = [5,7,7,8,8,10], target = 6
**Output:** [-1,-1]
<strong class="example">Example 3:**

**Input:** nums = [], target = 0
**Output:** [-1,-1]

 

**Constraints:**



	- `0 <= nums.length <= 10^5`
	- `-10^9 <= nums[i] <= 10^9`
	- `nums` is a non-decreasing array.
	- `-10^9 <= target <= 10^9`

---

## 💻 My Solution

```cpp
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        int l=lower_bound(nums.begin(),nums.end(),target)-nums.begin();
        int r=upper_bound(nums.begin(),nums.end(),target)-nums.begin()-1;

        if(l==nums.size() || nums[l]!=target) return {-1,-1};

        return {l,r};
    }
};

```

---

## 🧪 Sample Test Case

```
[5,7,7,8,8,10]
8
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(log n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
