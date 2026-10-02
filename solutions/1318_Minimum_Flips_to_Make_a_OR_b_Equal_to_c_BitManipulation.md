<div align="center">

# ⚡ 1318. Minimum Flips to Make a OR b Equal to c

*Pushed on October 02, 2026 · Problem #117 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | ⚡ Bit Manipulation   |
| **Time Complexity**  | ⏱️ `O(1)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 72.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `Bit Manipulation`

---

## 🧩 Problem Description

Given 3 positives numbers `a`, `b` and `c`. Return the minimum flips required in some bits of `a` and `b` to make ( `a` OR `b` == `c` ). (bitwise OR operation).<br />
Flip operation consists of change **any** single bit 1 to 0 or change the bit 0 to 1 in their binary representation.


 

<strong class="example">Example 1:**


<img alt="" src="https://assets.leetcode.com/uploads/2020/01/06/sample_3_1676.png" style="width: 260px; height: 87px;" />



**Input:** a = 2, b = 6, c = 5
**Output:** 3
**Explanation: **After flips a = 1 , b = 4 , c = 5 such that (`a` OR `b` == `c`)

<strong class="example">Example 2:**



**Input:** a = 4, b = 2, c = 7
**Output:** 1


<strong class="example">Example 3:**



**Input:** a = 1, b = 2, c = 3
**Output:** 0


 

**Constraints:**



	- `1 <= a <= 10^9`
	- `1 <= b <= 10^9`
	- `1 <= c <= 10^9`

---

## 🪄 Hints
> 💡 Check the bits one by one whether they need to be flipped.

## 💻 My Solution

```python
class Solution(object):
    def minFlips(self, a, b, c):
        """
        :type a: int
        :type b: int
        :type c: int
        :rtype: int
        """
        flips = 0

        while a or b or c:
            abit = a & 1
            bbit = b & 1
            cbit = c & 1

            if cbit == 0:
                flips += abit + bbit
            else:
                if abit == 0 and bbit == 0:
                    flips += 1

            a >>= 1
            b >>= 1
            c >>= 1

        return flips
        

```

---

## 🧪 Sample Test Case

```
2
6
5
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Bit Manipulation** techniques.
> The key insight is to leverage `O(1)` time complexity
> by applying bit manipulation to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
