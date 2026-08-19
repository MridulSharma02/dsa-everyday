<div align="center">

# 📦 198. House Robber

*Pushed on August 19, 2026 · Problem #73 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 53.5%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Dynamic Programming`

---

## 🧩 Problem Description

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and <b>it will automatically contact the police if two adjacent houses were broken into on the same night</b>.


Given an integer array `nums` representing the amount of money of each house, return *the maximum amount of money you can rob tonight <b>without alerting the police</b>*.


 

<strong class="example">Example 1:**



**Input:** nums = [1,2,3,1]
**Output:** 4
**Explanation:** Rob house 1 (money = 1) and then rob house 3 (money = 3).
Total amount you can rob = 1 + 3 = 4.


<strong class="example">Example 2:**



**Input:** nums = [2,7,9,3,1]
**Output:** 12
**Explanation:** Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
Total amount you can rob = 2 + 9 + 1 = 12.


 

**Constraints:**



	- `1 <= nums.length <= 100`
	- `0 <= nums[i] <= 400`

---

## 💻 My Solution

```python
class Solution(object):
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        prev, curr = 0, 0
        
        for num in nums:
            temp = curr
            curr = max(curr, prev + num)
            prev = temp
        
        return curr

```

---

## 🧪 Sample Test Case

```
[1,2,3,1]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
