<div align="center">

# 📦 1004. Max Consecutive Ones III

*Pushed on September 17, 2026 · Problem #102 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 68.5%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Binary Search` `Sliding Window` `Prefix Sum`

---

## 🧩 Problem Description

Given a binary array `nums` and an integer `k`, return *the maximum number of consecutive *`1`*&#39;s in the array if you can flip at most* `k` `0`&#39;s.


 

<strong class="example">Example 1:**



**Input:** nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
**Output:** 6
**Explanation:** [1,1,1,0,0,<u>**1**,1,1,1,1,**1**</u>]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.

<strong class="example">Example 2:**



**Input:** nums = [0,0,1,1,0,0,1,1,1,0,1,1,0,0,0,1,1,1,1], k = 3
**Output:** 10
**Explanation:** [0,0,<u>1,1,**1**,**1**,1,1,1,**1**,1,1</u>,0,0,0,1,1,1,1]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.


 

**Constraints:**



	- `1 <= nums.length <= 10^5`
	- `nums[i]` is either 0 or 1.
	- `0 <= k <= nums.length`

---

## 🪄 Hints
> 💡 One thing's for sure, we will only flip a zero if it extends an existing window of 1s. Otherwise, there's no point in doing it, right? Think Sliding Window!
> 💡 Since we know this problem can be solved using the sliding window construct, we might as well focus in that direction for hints. Basically, in a given window, we can never have > K zeros, right?

## 💻 My Solution

```python
class Solution(object):
    def longestOnes(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        left = 0
        zeros = 0
        ans = 0

        for right in range(len(nums)):
            if nums[right] == 0:
                zeros += 1

            while zeros > k:
                if nums[left] == 0:
                    zeros -= 1
                left += 1

            ans = max(ans, right - left + 1)

        return ans     

```

---

## 🧪 Sample Test Case

```
[1,1,1,0,0,0,1,1,1,1,0]
2
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
