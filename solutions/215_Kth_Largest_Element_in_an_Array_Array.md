<div align="center">

# 📦 215. Kth Largest Element in an Array

*Pushed on September 02, 2026 · Problem #87 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 69.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Divide and Conquer` `Sorting` `Heap (Priority Queue)` `Quickselect`

---

## 🧩 Problem Description

Given an integer array `nums` and an integer `k`, return *the* `k^th` *largest element in the array*.


Note that it is the `k^th` largest element in the sorted order, not the `k^th` distinct element.


Can you solve it without sorting?


 

<strong class="example">Example 1:**

**Input:** nums = [3,2,1,5,6,4], k = 2
**Output:** 5
<strong class="example">Example 2:**

**Input:** nums = [3,2,3,1,2,4,5,5,6], k = 4
**Output:** 4

 

**Constraints:**



	- `1 <= k <= nums.length <= 10^5`
	- `-10^4 <= nums[i] <= 10^4`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int findKthLargest(vector<int>& nums, int k) {
        priority_queue<int, vector<int>, greater<int>> pq;

        for (int num : nums) {
            pq.push(num);

            if (pq.size() > k)
                pq.pop();
        }

        return pq.top();
    }
};

```

---

## 🧪 Sample Test Case

```
[3,2,1,5,6,4]
2
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
