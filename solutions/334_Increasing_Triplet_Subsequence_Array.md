<div align="center">

# 📦 334. Increasing Triplet Subsequence

*Pushed on August 22, 2026 · Problem #76 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 39.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Greedy` `Longest Increasing Subsequence`

---

## 🧩 Problem Description

Given an integer array `nums`, return `true`* if there exists a triple of indices *`(i, j, k)`* such that *`i < j < k`* and *`nums[i] < nums[j] < nums[k]`. If no such indices exists, return `false`.


 

<strong class="example">Example 1:**



**Input:** nums = [1,2,3,4,5]
**Output:** true
**Explanation:** Any triplet where i < j < k is valid.


<strong class="example">Example 2:**



**Input:** nums = [5,4,3,2,1]
**Output:** false
**Explanation:** No triplet exists.


<strong class="example">Example 3:**



**Input:** nums = [2,1,5,0,4,6]
**Output:** true
**Explanation:** One of the valid triplet is (1, 4, 5), because nums[1] == 1 < nums[4] == 4 < nums[5] == 6.


 

**Constraints:**



	- `1 <= nums.length <= 5 * 10^5`
	- `-2^31 <= nums[i] <= 2^31 - 1`


 

**Follow up:** Could you implement a solution that runs in `O(n)` time complexity and `O(1)` space complexity?

---

## 💻 My Solution

```python
class Solution(object):
    def increasingTriplet(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        first=float('inf')
        second=float('inf')

        for x in nums:
            if x <= first:
                first=x
            elif x <= second:
                second=x
            else:
                return True

        return False

```

---

## 🧪 Sample Test Case

```
[1,2,3,4,5]
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
