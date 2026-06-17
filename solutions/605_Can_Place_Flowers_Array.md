<div align="center">

# 📦 605. Can Place Flowers

*Pushed on June 17, 2026 · Problem #10 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 29.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Greedy`

---

## 🧩 Problem Description

You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in **adjacent** plots.


Given an integer array `flowerbed` containing `0`&#39;s and `1`&#39;s, where `0` means empty and `1` means not empty, and an integer `n`, return `true` *if* `n` *new flowers can be planted in the* `flowerbed` *without violating the no-adjacent-flowers rule and* `false` *otherwise*.


 

<strong class="example">Example 1:**

**Input:** flowerbed = [1,0,0,0,1], n = 1
**Output:** true
<strong class="example">Example 2:**

**Input:** flowerbed = [1,0,0,0,1], n = 2
**Output:** false

 

**Constraints:**



	- `1 <= flowerbed.length <= 2 * 10^4`
	- `flowerbed[i]` is `0` or `1`.
	- There are no two adjacent flowers in `flowerbed`.
	- `0 <= n <= flowerbed.length`

---

## 💻 My Solution

```python
class Solution(object):
    def canPlaceFlowers(self, flowerbed, n):
        """
        :type flowerbed: List[int]
        :type n: int
        :rtype: bool
        """
        a = len(flowerbed)

        if n == 0:
            return True

        for i in range(a):
            if a == 1 and flowerbed[i] == 0:
                flowerbed[i] = 1
                n -= 1

            elif i == 0 and flowerbed[i] == 0 and flowerbed[i+1] == 0:
                flowerbed[i] = 1
                n -= 1

            elif i == a-1 and flowerbed[i] == 0 and flowerbed[i-1] == 0:
                flowerbed[i] = 1
                n -= 1

            elif i > 0 and i < a-1 and flowerbed[i] == 0 and flowerbed[i-1] == 0 and flowerbed[i+1] == 0:
                flowerbed[i] = 1
                n -= 1

        return n <= 0

```

---

## 🧪 Sample Test Case

```
[1,0,0,0,1]
1
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
