<div align="center">

# 📦 1493. Longest Subarray of 1's After Deleting One Element

*Pushed on September 12, 2026 · Problem #97 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 71.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Dynamic Programming` `Sliding Window`

---

## 🧩 Problem Description

Given a binary array `nums`, you should delete one element from it.


Return *the size of the longest non-empty subarray containing only *`1`*&#39;s in the resulting array*. Return `0` if there is no such subarray.


 

<strong class="example">Example 1:**



**Input:** nums = [1,1,0,1]
**Output:** 3
**Explanation:** After deleting the number in position 2, [1,1,1] contains 3 numbers with value of 1&#39;s.


<strong class="example">Example 2:**



**Input:** nums = [0,1,1,1,0,1,1,0,1]
**Output:** 5
**Explanation:** After deleting the number in position 4, [0,1,1,1,1,1,0,1] longest subarray with value of 1&#39;s is [1,1,1,1,1].


<strong class="example">Example 3:**



**Input:** nums = [1,1,1]
**Output:** 2
**Explanation:** You must delete one element.


 

**Constraints:**



	- `1 <= nums.length <= 10^5`
	- `nums[i]` is either `0` or `1`.

---

## 🪄 Hints
> 💡 Maintain a sliding window where there is at most one zero in it.

## 💻 My Solution

```python
class Solution(object):
    def longestSubarray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        left = 0
        zeros = 0
        ans = 0

        for right in range(len(nums)):
            if nums[right] == 0:
                zeros += 1

            while zeros > 1:
                if nums[left] == 0:
                    zeros -= 1
                left += 1

            ans = max(ans, right - left)

        return ans       

```

---

## 🧪 Sample Test Case

```
[1,1,0,1]
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
