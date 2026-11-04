<div align="center">

# 🔢 9. Palindrome Number

*Pushed on November 04, 2026 · Problem #150 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 61.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `Math`

---

## 🧩 Problem Description

Given an integer `x`, return `true` if `x` is a <span data-keyword="palindrome-integer">**palindrome**</span>, and `false` otherwise.


 

<strong class="example">Example 1:**



**Input:** x = 121
**Output:** true
**Explanation:** 121 reads as 121 from left to right and from right to left.


<strong class="example">Example 2:**



**Input:** x = -121
**Output:** false
**Explanation:** From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.


<strong class="example">Example 3:**



**Input:** x = 10
**Output:** false
**Explanation:** Reads 01 from right to left. Therefore it is not a palindrome.


 

**Constraints:**



	- `-2^31 <= x <= 2^31 - 1`


 

**Follow up:** Could you solve it without converting the integer to a string?

---

## 🪄 Hints
> 💡 Beware of overflow when you reverse the integer.

## 💻 My Solution

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x < 0 or (x % 10 == 0 and x != 0):
            return False
        reversed_half = 0
        while x > reversed_half:
            digit = x % 10
            reversed_half = reversed_half * 10 + digit
            x //= 10
        return x == reversed_half or x == reversed_half // 10

```

---

## 🧪 Sample Test Case

```
121
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Math** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying math to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
