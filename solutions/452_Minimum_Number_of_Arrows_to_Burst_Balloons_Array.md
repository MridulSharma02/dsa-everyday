<div align="center">

# 📦 452. Minimum Number of Arrows to Burst Balloons

*Pushed on October 03, 2026 · Problem #118 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 62.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Greedy` `Sorting`

---

## 🧩 Problem Description

There are some spherical balloons taped onto a flat wall that represents the XY-plane. The balloons are represented as a 2D integer array `points` where `points[i] = [xstart, xend]` denotes a balloon whose **horizontal diameter** stretches between `xstart` and `xend`. You do not know the exact y-coordinates of the balloons.


Arrows can be shot up **directly vertically** (in the positive y-direction) from different points along the x-axis. A balloon with `xstart` and `xend` is **burst** by an arrow shot at `x` if `xstart <= x <= xend`. There is **no limit** to the number of arrows that can be shot. A shot arrow keeps traveling up infinitely, bursting any balloons in its path.


Given the array `points`, return *the **minimum** number of arrows that must be shot to burst all balloons*.


 

<strong class="example">Example 1:**



**Input:** points = [[10,16],[2,8],[1,6],[7,12]]
**Output:** 2
**Explanation:** The balloons can be burst by 2 arrows:
- Shoot an arrow at x = 6, bursting the balloons [2,8] and [1,6].
- Shoot an arrow at x = 11, bursting the balloons [10,16] and [7,12].


<strong class="example">Example 2:**



**Input:** points = [[1,2],[3,4],[5,6],[7,8]]
**Output:** 4
**Explanation:** One arrow needs to be shot for each balloon for a total of 4 arrows.


<strong class="example">Example 3:**



**Input:** points = [[1,2],[2,3],[3,4],[4,5]]
**Output:** 2
**Explanation:** The balloons can be burst by 2 arrows:
- Shoot an arrow at x = 2, bursting the balloons [1,2] and [2,3].
- Shoot an arrow at x = 4, bursting the balloons [3,4] and [4,5].


 

**Constraints:**



	- `1 <= points.length <= 10^5`
	- `points[i].length == 2`
	- `-2^31 <= xstart < xend <= 2^31 - 1`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int findMinArrowShots(vector<vector<int>>& points) {
        sort(points.begin(), points.end(),
             [](auto& a, auto& b) {
                 return a[1] < b[1];
             });

        int arrows = 1;
        long long end = points[0][1];

        for (int i = 1; i < points.size(); i++) {
            if (points[i][0] > end) {
                arrows++;
                end = points[i][1];
            }
        }

        return arrows;
    }
};

```

---

## 🧪 Sample Test Case

```
[[10,16],[2,8],[1,6],[7,12]]
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
