<div align="center">

# 📦 238. Product of Array Except Self

*Pushed on November 10, 2026 · Problem #156 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 69.4%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Prefix Sum`

---

## 🧩 Problem Description

Given an integer array `nums`, return *an array* `answer` *such that* `answer[i]` *is equal to the product of all the elements of* `nums` *except* `nums[i]`.


The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.


You must write an algorithm that runs in `O(n)` time and without using the division operation.


 

<strong class="example">Example 1:**

**Input:** nums = [1,2,3,4]
**Output:** [24,12,8,6]
<strong class="example">Example 2:**

**Input:** nums = [-1,1,0,-3,3]
**Output:** [0,0,9,0,0]

 

**Constraints:**



	- `2 <= nums.length <= 10^5`
	- `-30 <= nums[i] <= 30`
	- The input is generated such that `answer[i]` is **guaranteed** to fit in a **32-bit** integer.


 

**Follow up:** Can you solve the problem in `O(1)` extra space complexity? (The output array **does not** count as extra space for space complexity analysis.)

---

## 🪄 Hints
> 💡 Think how you can efficiently utilize prefix and suffix products to calculate the product of all elements except self for each index. Can you pre-compute the prefix and suffix products in linear time to avoid redundant calculations?
> 💡 Can you minimize additional space usage by reusing memory or modifying the input array to store intermediate results?

## 💻 My Solution

```python
class Solution(object):
    def productExceptSelf(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        n=len(nums)
        answer=[1]*n

        prefix=1
        for i in range(n):
            answer[i]=prefix
            prefix*=nums[i]

        suffix=1
        for i in range(n-1,-1,-1):
            answer[i]*=suffix
            suffix*=nums[i]

        return answer

```

---

## 🧪 Sample Test Case

```
[1,2,3,4]
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
