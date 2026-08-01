<div align="center">

# 📦 287. Find the Duplicate Number

*Pushed on August 01, 2026 · Problem #55 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.7%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Two Pointers` `Binary Search` `Bit Manipulation`

---

## 🧩 Problem Description

Given an array of integers `nums` containing `n + 1` integers where each integer is in the range `[1, n]` inclusive.


There is only **one repeated number** in `nums`, return *this repeated number*.


You must solve the problem **without** modifying the array `nums` and using only constant extra space.


 

<strong class="example">Example 1:**



**Input:** nums = [1,3,4,2,2]
**Output:** 2


<strong class="example">Example 2:**



**Input:** nums = [3,1,3,4,2]
**Output:** 3


<strong class="example">Example 3:**



**Input:** nums = [3,3,3,3,3]
**Output:** 3

 

**Constraints:**



	- `1 <= n <= 10^5`
	- `nums.length == n + 1`
	- `1 <= nums[i] <= n`
	- All the integers in `nums` appear only **once** except for **precisely one integer** which appears **two or more** times.


 

<b>Follow up:</b>



	- How can we prove that at least one duplicate number must exist in `nums`?
	- Can you solve the problem in linear runtime complexity?

---

## 💻 My Solution

```python
class Solution(object):
    def findDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        slow=nums[0]
        fast=nums[0]
        while True:
            slow=nums[slow]           # Move 1 step
            fast=nums[nums[fast]]     # Move 2 steps
            if slow==fast:
                break
        slow=nums[0]
        while slow!=fast:
            slow=nums[slow]
            fast=nums[fast]
        return slow 
        

```

---

## 🧪 Sample Test Case

```
[1,3,4,2,2]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
