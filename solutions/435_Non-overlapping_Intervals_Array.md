<div align="center">

# 📦 435. Non-overlapping Intervals

*Pushed on October 13, 2026 · Problem #128 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 57.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Dynamic Programming` `Greedy` `Sorting`

---

## 🧩 Problem Description

Given an array of intervals `intervals` where `intervals[i] = [starti, endi]`, return *the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping*.


**Note** that intervals which only touch at a point are **non-overlapping**. For example, `[1, 2]` and `[2, 3]` are non-overlapping.


 

<strong class="example">Example 1:**



**Input:** intervals = [[1,2],[2,3],[3,4],[1,3]]
**Output:** 1
**Explanation:** [1,3] can be removed and the rest of the intervals are non-overlapping.


<strong class="example">Example 2:**



**Input:** intervals = [[1,2],[1,2],[1,2]]
**Output:** 2
**Explanation:** You need to remove two [1,2] to make the rest of the intervals non-overlapping.


<strong class="example">Example 3:**



**Input:** intervals = [[1,2],[2,3]]
**Output:** 0
**Explanation:** You don&#39;t need to remove any of the intervals since they&#39;re already non-overlapping.


 

**Constraints:**



	- `1 <= intervals.length <= 10^5`
	- `intervals[i].length == 2`
	- `-5 * 10^4 <= starti < endi <= 5 * 10^4`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int eraseOverlapIntervals(vector<vector<int>>& intervals) {
        sort(intervals.begin(), intervals.end(),
             [](auto& a, auto& b) {
                 return a[1] < b[1];
             });

        int count = 0;
        int end = intervals[0][1];

        for (int i = 1; i < intervals.size(); i++) {
            if (intervals[i][0] < end) {
                count++;
            } else {
                end = intervals[i][1];
            }
        }

        return count;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1,2],[2,3],[3,4],[1,3]]
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
