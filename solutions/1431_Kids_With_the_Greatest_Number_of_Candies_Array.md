<div align="center">

# 📦 1431. Kids With the Greatest Number of Candies

*Pushed on August 31, 2026 · Problem #85 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 88.0%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array`

---

## 🧩 Problem Description

There are `n` kids with candies. You are given an integer array `candies`, where each `candies[i]` represents the number of candies the `i^th` kid has, and an integer `extraCandies`, denoting the number of extra candies that you have.


Return *a boolean array *`result`* of length *`n`*, where *`result[i]`* is *`true`* if, after giving the *`i^th`* kid all the *`extraCandies`*, they will have the **greatest** number of candies among all the kids**, or *`false`* otherwise*.


Note that **multiple** kids can have the **greatest** number of candies.


 

<strong class="example">Example 1:**



**Input:** candies = [2,3,5,1,3], extraCandies = 3
**Output:** [true,true,true,false,true] 
**Explanation:** If you give all extraCandies to:
- Kid 1, they will have 2 + 3 = 5 candies, which is the greatest among the kids.
- Kid 2, they will have 3 + 3 = 6 candies, which is the greatest among the kids.
- Kid 3, they will have 5 + 3 = 8 candies, which is the greatest among the kids.
- Kid 4, they will have 1 + 3 = 4 candies, which is not the greatest among the kids.
- Kid 5, they will have 3 + 3 = 6 candies, which is the greatest among the kids.


<strong class="example">Example 2:**



**Input:** candies = [4,2,1,1,2], extraCandies = 1
**Output:** [true,false,false,false,false] 
**Explanation:** There is only 1 extra candy.
Kid 1 will always have the greatest number of candies, even if a different kid is given the extra candy.


<strong class="example">Example 3:**



**Input:** candies = [12,1,12], extraCandies = 10
**Output:** [true,false,true]


 

**Constraints:**



	- `n == candies.length`
	- `2 <= n <= 100`
	- `1 <= candies[i] <= 100`
	- `1 <= extraCandies <= 50`

---

## 🪄 Hints
> 💡 For each kid check if candies[i] + extraCandies ≥ maximum in Candies[i].

## 💻 My Solution

```python
class Solution(object):
    def kidsWithCandies(self, candies, extraCandies):
        """
        :type candies: List[int]
        :type extraCandies: int
        :rtype: List[bool]
        """
        maxi=0
        result=[]
        for i in candies:
            if i>maxi:
                maxi=i
        for i in candies:
            if (i+extraCandies)>=maxi:
                result+=[True]
            else:
                result+=[False]
        return result

```

---

## 🧪 Sample Test Case

```
[2,3,5,1,3]
3
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
