<div align="center">

# 📦 735. Asteroid Collision

*Pushed on June 11, 2026 · Problem #4 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 48.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `Array` `Stack` `Simulation`

---

## 🧩 Problem Description

We are given an array `asteroids` of integers representing asteroids in a row. The indices of the asteroid in the array represent their relative position in space.


For each asteroid, the absolute value represents its size, and the sign represents its direction (positive meaning right, negative meaning left). Each asteroid moves at the same speed.


Find out the state of the asteroids after all collisions. If two asteroids meet, the smaller one will explode. If both are the same size, both will explode. Two asteroids moving in the same direction will never meet.


 

<strong class="example">Example 1:**



**Input:** asteroids = [5,10,-5]
**Output:** [5,10]
**Explanation:** The 10 and -5 collide resulting in 10. The 5 and 10 never collide.


<strong class="example">Example 2:**



**Input:** asteroids = [8,-8]
**Output:** []
**Explanation:** The 8 and -8 collide exploding each other.


<strong class="example">Example 3:**



**Input:** asteroids = [10,2,-5]
**Output:** [10]
**Explanation:** The 2 and -5 collide resulting in -5. The 10 and -5 collide resulting in 10.


<strong class="example">Example 4:**



**Input:** asteroids = [3,5,-6,2,-1,4]​​​​​​​
**Output:** [-6,2,4]
**Explanation:** The asteroid -6 makes the asteroid 3 and 5 explode, and then continues going left. On the other side, the asteroid 2 makes the asteroid -1 explode and then continues going right, without reaching asteroid 4.


 

**Constraints:**



	- `2 <= asteroids.length <= 10^4`
	- `-1000 <= asteroids[i] <= 1000`
	- `asteroids[i] != 0`

---

## 🪄 Hints
> 💡 Say a row of asteroids is stable.  What happens when a new asteroid is added on the right?

## 💻 My Solution

```python
class Solution(object):
    def asteroidCollision(self, asteroids):
        """
        :type asteroids: List[int]
        :rtype: List[int]
        """
        stack = []

        for ast in asteroids:
            while stack and ast < 0 and stack[-1] > 0:
                if stack[-1] < -ast:
                    stack.pop()
                    continue
                elif stack[-1] == -ast:
                    stack.pop()
                break
            else:
                stack.append(ast)

        return stack       

```

---

## 🧪 Sample Test Case

```
[5,10,-5]
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
