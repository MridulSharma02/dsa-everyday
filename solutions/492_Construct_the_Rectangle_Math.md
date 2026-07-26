<div align="center">

# 🔢 492. Construct the Rectangle

*Pushed on July 26, 2026 · Problem #49 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math`

---

## 🧩 Problem Description

A web developer needs to know how to design a web page&#39;s size. So, given a specific rectangular web page&rsquo;s area, your job by now is to design a rectangular web page, whose length L and width W satisfy the following requirements:



	- The area of the rectangular web page you designed must equal to the given target area.
	- The width `W` should not be larger than the length `L`, which means `L >= W`.
	- The difference between length `L` and width `W` should be as small as possible.


Return *an array `[L, W]` where `L` and `W` are the length and width of the web page you designed in sequence.*


 

<strong class="example">Example 1:**



**Input:** area = 4
**Output:** [2,2]
**Explanation:** The target area is 4, and all the possible ways to construct it are [1,4], [2,2], [4,1]. 
But according to requirement 2, [1,4] is illegal; according to requirement 3,  [4,1] is not optimal compared to [2,2]. So the length L is 2, and the width W is 2.


<strong class="example">Example 2:**



**Input:** area = 37
**Output:** [37,1]


<strong class="example">Example 3:**



**Input:** area = 122122
**Output:** [427,286]


 

**Constraints:**



	- `1 <= area <= 10^7`

---

## 🪄 Hints
> 💡 The W is always less than or equal to the square root of the area, so we start searching at sqrt(area) till we find the result.

## 💻 My Solution

```cpp
class Solution {
public:
    vector<int> constructRectangle(int area) {
        int w=sqrt(area);

        while(area%w!=0)
            w--;

        return {area/w,w};
    }
};

```

---

## 🧪 Sample Test Case

```
4
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
