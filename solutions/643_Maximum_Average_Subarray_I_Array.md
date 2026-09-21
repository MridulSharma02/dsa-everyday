<div align="center">

# 📦 643. Maximum Average Subarray I

*Pushed on September 21, 2026 · Problem #106 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 49.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Sliding Window`

---

## 🧩 Problem Description

You are given an integer array `nums` consisting of `n` elements, and an integer `k`.


Find a contiguous subarray whose **length is equal to** `k` that has the maximum average value and return *this value*. Any answer with a calculation error less than `10^-5` will be accepted.


 

<strong class="example">Example 1:**



**Input:** nums = [1,12,-5,-6,50,3], k = 4
**Output:** 12.75000
**Explanation:** Maximum average is (12 - 5 - 6 + 50) / 4 = 51 / 4 = 12.75


<strong class="example">Example 2:**



**Input:** nums = [5], k = 1
**Output:** 5.00000


 

**Constraints:**



	- `n == nums.length`
	- `1 <= k <= n <= 10^5`
	- `-10^4 <= nums[i] <= 10^4`

---

## 💻 My Solution

```python
class Solution(object):
    def findMaxAverage(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: float
        """
        a=sum(nums[:k])
        s=a

        for i in range(k,len(nums)):
            a=a-nums[i-k]+nums[i]
            if a>s:
                s=a
        return float(s)/k

```

---

## 🧪 Sample Test Case

```
[1,12,-5,-6,50,3]
4
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
