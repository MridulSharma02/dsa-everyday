<div align="center">

# 📦 4. Median of Two Sorted Arrays

*Pushed on September 27, 2026 · Problem #112 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 47.7%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Binary Search` `Divide and Conquer`

---

## 🧩 Problem Description

Given two sorted arrays `nums1` and `nums2` of size `m` and `n` respectively, return **the median** of the two sorted arrays.


The overall run time complexity should be `O(log (m+n))`.


 

<strong class="example">Example 1:**



**Input:** nums1 = [1,3], nums2 = [2]
**Output:** 2.00000
**Explanation:** merged array = [1,2,3] and median is 2.


<strong class="example">Example 2:**



**Input:** nums1 = [1,2], nums2 = [3,4]
**Output:** 2.50000
**Explanation:** merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.


 

**Constraints:**



	- `nums1.length == m`
	- `nums2.length == n`
	- `0 <= m <= 1000`
	- `0 <= n <= 1000`
	- `1 <= m + n <= 2000`
	- `-10^6 <= nums1[i], nums2[i] <= 10^6`

---

## 💻 My Solution

```python
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        nums3 = []
        i = j = 0
        while i < len(nums1) and j < len(nums2):
            if nums1[i] < nums2[j]:
                nums3.append(nums1[i])
                i += 1
            else:
                nums3.append(nums2[j])
                j += 1
        nums3.extend(nums1[i:])
        nums3.extend(nums2[j:])
        
        n = len(nums3)
        if n % 2 == 0:
            return (nums3[n//2 - 1] + nums3[n//2]) / 2.0
        else:
            return nums3[n//2]

```

---

## 🧪 Sample Test Case

```
[1,3]
[2]
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
