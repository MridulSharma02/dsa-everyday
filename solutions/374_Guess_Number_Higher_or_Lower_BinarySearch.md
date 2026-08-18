<div align="center">

# 🔍 374. Guess Number Higher or Lower

*Pushed on August 18, 2026 · Problem #72 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔍 Binary Search   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 58.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Binary Search` `Interactive`

---

## 🧩 Problem Description

We are playing the Guess Game. The game is as follows:


I pick a number from `1` to `n`. You have to guess which number I picked (the number I picked stays the same throughout the game).


Every time you guess wrong, I will tell you whether the number I picked is higher or lower than your guess.


You call a pre-defined API `int guess(int num)`, which returns three possible results:



	- `-1`: Your guess is higher than the number I picked (i.e. `num > pick`).
	- `1`: Your guess is lower than the number I picked (i.e. `num < pick`).
	- `0`: your guess is equal to the number I picked (i.e. `num == pick`).


Return *the number that I picked*.


 

<strong class="example">Example 1:**



**Input:** n = 10, pick = 6
**Output:** 6


<strong class="example">Example 2:**



**Input:** n = 1, pick = 1
**Output:** 1


<strong class="example">Example 3:**



**Input:** n = 2, pick = 1
**Output:** 1


 

**Constraints:**



	- `1 <= n <= 2^31 - 1`
	- `1 <= pick <= n`

---

## 💻 My Solution

```python
# The guess API is already defined for you.
# @param num, your guess
# @return -1 if num is higher than the picked number
#          1 if num is lower than the picked number
#          otherwise return 0
# def guess(num):

class Solution(object):
    def guessNumber(self, n):
        """
        :type n: int
        :rtype: int
        """
        left, right = 1, n

        while left <= right:
            mid = (left + right) // 2
            res = guess(mid)

            if res == 0:
                return mid
            elif res == -1:
                right = mid - 1
            else:
                left = mid + 1
        

```

---

## 🧪 Sample Test Case

```
10
6
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Binary Search** techniques.
> The key insight is to leverage `O(log n)` time complexity
> by applying binary search to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
