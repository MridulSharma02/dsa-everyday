<div align="center">

# 📦 1. Two Sum

*Pushed on June 08, 2026 · Problem #1 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 57.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Hash Table`

---

## 🧩 Problem Description

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.


You may assume that each input would have ***exactly* one solution**, and you may not use the *same* element twice.


You can return the answer in any order.


 

<strong class="example">Example 1:**



**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].


<strong class="example">Example 2:**



**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]


<strong class="example">Example 3:**



**Input:** nums = [3,3], target = 6
**Output:** [0,1]


 

**Constraints:**



	- `2 <= nums.length <= 10^4`
	- `-10^9 <= nums[i] <= 10^9`
	- `-10^9 <= target <= 10^9`
	- **Only one valid answer exists.**


 

**Follow-up: **Can you come up with an algorithm that is less than `O(n^2)`<font face="monospace"> </font>time complexity?

---

## 🪄 Hints
> 💡 A really brute force way would be to search for all possible pairs of numbers but that would be too slow. Again, it's best to try out brute force solutions just for completeness. It is from these brute force solutions that you can come up with optimizations.
> 💡 So, if we fix one of the numbers, say <code>x</code>, we have to scan the entire array to find the next number <code>y</code> which is <code>value - x</code> where value is the input parameter. Can we change our array somehow so that this search becomes faster?

## 💻 My Solution

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        n = len(nums)
        
        for i in range(n):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]

```

---

## 🧪 Sample Test Case

```
[2,7,11,15]
9
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
