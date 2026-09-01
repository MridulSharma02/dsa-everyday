<div align="center">

# 📦 875. Koko Eating Bananas

*Pushed on September 01, 2026 · Problem #86 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 50.5%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Binary Search`

---

## 🧩 Problem Description

Koko loves to eat bananas. There are `n` piles of bananas, the `i^th` pile has `piles[i]` bananas. The guards have gone and will come back in `h` hours.


Koko can decide her bananas-per-hour eating speed of `k`. Each hour, she chooses some pile of bananas and eats `k` bananas from that pile. If the pile has less than `k` bananas, she eats all of them instead and will not eat any more bananas during this hour.


Koko likes to eat slowly but still wants to finish eating all the bananas before the guards return.


Return *the minimum integer* `k` *such that she can eat all the bananas within* `h` *hours*.


 

<strong class="example">Example 1:**



**Input:** piles = [3,6,7,11], h = 8
**Output:** 4


<strong class="example">Example 2:**



**Input:** piles = [30,11,23,4,20], h = 5
**Output:** 30


<strong class="example">Example 3:**



**Input:** piles = [30,11,23,4,20], h = 6
**Output:** 23


 

**Constraints:**



	- `1 <= piles.length <= 10^4`
	- `piles.length <= h <= 10^9`
	- `1 <= piles[i] <= 10^9`

---

## 💻 My Solution

```python
class Solution(object):
    def minEatingSpeed(self, piles, h):
        """
        :type piles: List[int]
        :type h: int
        :rtype: int
        """
        left, right = 1, max(piles)

        while left < right:
            mid = (left + right) // 2

            hours = 0
            for pile in piles:
                hours += (pile + mid - 1) // mid

            if hours <= h:
                right = mid
            else:
                left = mid + 1

        return left

```

---

## 🧪 Sample Test Case

```
[3,6,7,11]
8
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
