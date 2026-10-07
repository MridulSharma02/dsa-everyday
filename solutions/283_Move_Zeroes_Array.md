<div align="center">

# 📦 283. Move Zeroes

*Pushed on October 07, 2026 · Problem #122 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.5%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Two Pointers`

---

## 🧩 Problem Description

Given an integer array `nums`, move all `0`&#39;s to the end of it while maintaining the relative order of the non-zero elements.


**Note** that you must do this in-place without making a copy of the array.


 

<strong class="example">Example 1:**

**Input:** nums = [0,1,0,3,12]
**Output:** [1,3,12,0,0]
<strong class="example">Example 2:**

**Input:** nums = [0]
**Output:** [0]

 

**Constraints:**



	- `1 <= nums.length <= 10^4`
	- `-2^31 <= nums[i] <= 2^31 - 1`


 

**Follow up:** Could you minimize the total number of operations done?

---

## 🪄 Hints
> 💡 <b>In-place</b> means we should not be allocating any space for extra array. But we are allowed to modify the existing array. However, as a first step, try coming up with a solution that makes use of additional space. For this problem as well, first apply the idea discussed using an additional array and the in-place solution will pop up eventually.
> 💡 A <b>two-pointer</b> approach could be helpful here. The idea would be to have one pointer for iterating the array and another pointer that just works on the non-zero elements of the array.

## 💻 My Solution

```python
class Solution(object):
    def moveZeroes(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        a=len(nums)
        count=0
        b=[]
        for i in nums:
            if i!=0:
                b+=[i]
            else:
                count+=1
        for i in range(count):
            b+=[0]
        nums[:]=b

```

---

## 🧪 Sample Test Case

```
[0,1,0,3,12]
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
