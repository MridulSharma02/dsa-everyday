<div align="center">

# 📦 11. Container With Most Water

*Pushed on June 22, 2026 · Problem #15 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 60.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Two Pointers` `Greedy`

---

## 🧩 Problem Description

You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `i^th` line are `(i, 0)` and `(i, height[i])`.


Find two lines that together with the x-axis form a container, such that the container contains the most water.


Return *the maximum amount of water a container can store*.


**Notice** that you may not slant the container.


 

<strong class="example">Example 1:**

<img alt="" src="https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg" style="width: 600px; height: 287px;" />

**Input:** height = [1,8,6,2,5,4,8,3,7]
**Output:** 49
**Explanation:** The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.


<strong class="example">Example 2:**



**Input:** height = [1,1]
**Output:** 1


 

**Constraints:**



	- `n == height.length`
	- `2 <= n <= 10^5`
	- `0 <= height[i] <= 10^4`

---

## 🪄 Hints
> 💡 If you simulate the problem, it will be O(n^2) which is not efficient.
> 💡 Try to use two-pointers. Set one pointer to the left and one to the right of the array. Always move the pointer that points to the lower line.

## 💻 My Solution

```python
class Solution(object):
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        left = 0
        right = len(height) - 1
        max_area = 0
        while left < right:
            width = right - left
            h = min(height[left], height[right])
            max_area = max(max_area, width * h)
            if height[left] < height[right]:
                left += 1
            else:
                right -= 1
        
        return max_area

```

---

## 🧪 Sample Test Case

```
[1,8,6,2,5,4,8,3,7]
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
