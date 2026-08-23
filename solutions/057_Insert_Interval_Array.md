<div align="center">

# 📦 57. Insert Interval

*Pushed on August 23, 2026 · Problem #77 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 45.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array`

---

## 🧩 Problem Description

You are given an array of non-overlapping intervals `intervals` where `intervals[i] = [starti, endi]` represent the start and the end of the `i^th` interval and `intervals` is sorted in ascending order by `starti`. You are also given an interval `newInterval = [start, end]` that represents the start and end of another interval.


Two intervals are considered overlapping if they share **at least** one point.


Insert `newInterval` into `intervals` such that `intervals` is still sorted in ascending order by `starti` and `intervals` still does not have any overlapping intervals (merge overlapping intervals if necessary).


Return `intervals`* after the insertion*.


**Note** that you don&#39;t need to modify `intervals` in-place. You can make a new array and return it.


 

<strong class="example">Example 1:**



**Input:** intervals = [[1,3],[6,9]], newInterval = [2,5]
**Output:** [[1,5],[6,9]]


<strong class="example">Example 2:**



**Input:** intervals = [[1,2],[3,5],[6,7],[8,10],[12,16]], newInterval = [4,8]
**Output:** [[1,2],[3,10],[12,16]]
**Explanation:** Because the new interval [4,8] overlaps with [3,5],[6,7],[8,10].


 

**Constraints:**



	- `0 <= intervals.length <= 10^4`
	- `intervals[i].length == 2`
	- `0 <= starti <= endi <= 10^5`
	- `intervals` is sorted by `starti` in **ascending** order.
	- `newInterval.length == 2`
	- `0 <= start <= end <= 10^5`

---

## 🪄 Hints
> 💡 Intervals Array is sorted. Can you use Binary Search to find the correct position to insert the new Interval.?
> 💡 Can you try merging the overlapping intervals while inserting the new interval?

## 💻 My Solution

```cpp
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
        vector<vector<int>> ans;
        int i=0,n=intervals.size();
        while(i<n && intervals[i][1]<newInterval[0])
            ans.push_back(intervals[i++]);
            
        while(i<n && intervals[i][0]<=newInterval[1]){
            newInterval[0]=min(newInterval[0],intervals[i][0]);
            newInterval[1]=max(newInterval[1],intervals[i][1]);
            i++;
        }
        ans.push_back(newInterval);
        while(i<n)
            ans.push_back(intervals[i++]);

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[[1,3],[6,9]]
[2,5]
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
