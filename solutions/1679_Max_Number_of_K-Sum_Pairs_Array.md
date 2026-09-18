<div align="center">

# 📦 1679. Max Number of K-Sum Pairs

*Pushed on September 18, 2026 · Problem #103 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 57.4%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Hash Table` `Two Pointers` `Sorting`

---

## 🧩 Problem Description

You are given an integer array `nums` and an integer `k`.


In one operation, you can pick two numbers from the array whose sum equals `k` and remove them from the array.


Return *the maximum number of operations you can perform on the array*.


 

<strong class="example">Example 1:**



**Input:** nums = [1,2,3,4], k = 5
**Output:** 2
**Explanation:** Starting with nums = [1,2,3,4]:
- Remove numbers 1 and 4, then nums = [2,3]
- Remove numbers 2 and 3, then nums = []
There are no more pairs that sum up to 5, hence a total of 2 operations.

<strong class="example">Example 2:**



**Input:** nums = [3,1,3,4,3], k = 6
**Output:** 1
**Explanation:** Starting with nums = [3,1,3,4,3]:
- Remove the first two 3&#39;s, then nums = [1,4,3]
There are no more pairs that sum up to 6, hence a total of 1 operation.

 

**Constraints:**



	- `1 <= nums.length <= 10^5`
	- `1 <= nums[i] <= 10^9`
	- `1 <= k <= 10^9`

---

## 🪄 Hints
> 💡 The abstract problem asks to count the number of disjoint pairs with a given sum k.
> 💡 For each possible value x, it can be paired up with k - x.

## 💻 My Solution

```python
class Solution(object):
    def maxOperations(self, nums, k):
        nums.sort()
        
        left = 0
        right = len(nums) - 1
        count = 0

        while left < right:
            s = nums[left] + nums[right]

            if s == k:
                count += 1
                left += 1
                right -= 1

            elif s < k:
                left += 1

            else:
                right -= 1

        return count

```

---

## 🧪 Sample Test Case

```
[1,2,3,4]
5
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
