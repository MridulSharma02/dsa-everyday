<div align="center">

# 📦 56. Merge Intervals

*Pushed on September 28, 2026 · Problem #113 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 52.9%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Sorting` `Quicksort`

---

## 🧩 Problem Description

Given an array of `intervals` where `intervals[i] = [starti, endi]`, merge all overlapping intervals, and return *an array of the non-overlapping intervals that cover all the intervals in the input*.


 

<strong class="example">Example 1:**



**Input:** intervals = [[1,3],[2,6],[8,10],[15,18]]
**Output:** [[1,6],[8,10],[15,18]]
**Explanation:** Since intervals [1,3] and [2,6] overlap, merge them into [1,6].


<strong class="example">Example 2:**



**Input:** intervals = [[1,4],[4,5]]
**Output:** [[1,5]]
**Explanation:** Intervals [1,4] and [4,5] are considered overlapping.


<strong class="example">Example 3:**



**Input:** intervals = [[4,7],[1,4]]
**Output:** [[1,7]]
**Explanation:** Intervals [1,4] and [4,7] are considered overlapping.


 

**Constraints:**



	- `1 <= intervals.length <= 10^4`
	- `intervals[i].length == 2`
	- `0 <= starti <= endi <= 10^4`

---

## 💻 My Solution

```python
class Solution(object):
    def merge(self, intervals):
        """
        :type intervals: List[List[int]]
        :rtype: List[List[int]]
        """
        if not intervals:
            return []
        # Sort by start time
        intervals.sort(key=lambda x: x[0])
        merged=[intervals[0]]
        for start,end in intervals[1:]:
            last_end=merged[-1][1]
            if start<=last_end:              # Overlapping intervals
                merged[-1][1]=max(last_end,end)  # Extend the interval
            else:
                merged.append([start,end])   # Non-overlapping, add new
        return merged

```

---

## 🧪 Sample Test Case

```
[[1,3],[2,6],[8,10],[15,18]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n log n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
