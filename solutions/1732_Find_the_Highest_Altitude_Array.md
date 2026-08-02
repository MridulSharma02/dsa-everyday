<div align="center">

# 📦 1732. Find the Highest Altitude

*Pushed on August 02, 2026 · Problem #56 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 84.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Prefix Sum`

---

## 🧩 Problem Description

There is a biker going on a road trip. The road trip consists of `n + 1` points at various altitudes. The biker starts his trip on point `0` with altitude equal `0`.


You are given an integer array `gain` of length `n` where `gain[i]` is the **net gain in altitude** between points `i`​​​​​​ and `i + 1` for all (`0 <= i < n)`. Return *the **highest altitude** of a point.*


 

<strong class="example">Example 1:**



**Input:** gain = [-5,1,5,0,-7]
**Output:** 1
**Explanation:** The altitudes are [0,-5,-4,1,1,-6]. The highest is 1.


<strong class="example">Example 2:**



**Input:** gain = [-4,-3,-2,-1,4,3,2]
**Output:** 0
**Explanation:** The altitudes are [0,-4,-7,-9,-10,-6,-3,-1]. The highest is 0.


 

**Constraints:**



	- `n == gain.length`
	- `1 <= n <= 100`
	- `-100 <= gain[i] <= 100`

---

## 🪄 Hints
> 💡 Let's note that the altitude of an element is the sum of gains of all the elements behind it
> 💡 Getting the altitudes can be done by getting the prefix sum array of the given array

## 💻 My Solution

```python
class Solution(object):
    def largestAltitude(self, gain):
        """
        :type gain: List[int]
        :rtype: int
        """
        max=0
        a=0
        for i in gain:
            a+=i
            if max<a:
                max=a
        return max


```

---

## 🧪 Sample Test Case

```
[-5,1,5,0,-7]
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
