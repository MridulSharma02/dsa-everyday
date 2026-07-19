<div align="center">

# 📦 724. Find Pivot Index

*Pushed on July 19, 2026 · Problem #42 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 63.3%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Prefix Sum`

---

## 🧩 Problem Description

Given an array of integers `nums`, calculate the **pivot index** of this array.


The **pivot index** is the index where the sum of all the numbers **strictly** to the left of the index is equal to the sum of all the numbers **strictly** to the index&#39;s right.


If the index is on the left edge of the array, then the left sum is `0` because there are no elements to the left. This also applies to the right edge of the array.


Return *the **leftmost pivot index***. If no such index exists, return `-1`.


 

<strong class="example">Example 1:**



**Input:** nums = [1,7,3,6,5,6]
**Output:** 3
**Explanation:**
The pivot index is 3.
Left sum = nums[0] + nums[1] + nums[2] = 1 + 7 + 3 = 11
Right sum = nums[4] + nums[5] = 5 + 6 = 11


<strong class="example">Example 2:**



**Input:** nums = [1,2,3]
**Output:** -1
**Explanation:**
There is no index that satisfies the conditions in the problem statement.

<strong class="example">Example 3:**



**Input:** nums = [2,1,-1]
**Output:** 0
**Explanation:**
The pivot index is 0.
Left sum = 0 (no elements to the left of index 0)
Right sum = nums[1] + nums[2] = 1 + -1 = 0


 

**Constraints:**



	- `1 <= nums.length <= 10^4`
	- `-1000 <= nums[i] <= 1000`


 

**Note:** This question is the same as 1991: <a href="https://leetcode.com/problems/find-the-middle-index-in-array/" target="_blank">https://leetcode.com/problems/find-the-middle-index-in-array/</a>

---

## 🪄 Hints
> 💡 Create an array sumLeft where sumLeft[i] is the sum of all the numbers to the left of index i.
> 💡 Create an array sumRight where sumRight[i] is the sum of all the numbers to the right of index i.

## 💻 My Solution

```python
class Solution(object):
    def pivotIndex(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        total = sum(nums)
        left = 0

        for i in range(len(nums)):
            right = total - left - nums[i]

            if left == right:
                return i

            left += nums[i]

        return -1
  

```

---

## 🧪 Sample Test Case

```
[1,7,3,6,5,6]
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
