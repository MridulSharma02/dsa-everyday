<div align="center">

# 🔢 1137. N-th Tribonacci Number

*Pushed on October 11, 2026 · Problem #126 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 63.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `Dynamic Programming` `Memoization`

---

## 🧩 Problem Description

The Tribonacci sequence Tn is defined as follows: 


T0 = 0, T1 = 1, T2 = 1, and Tn+3 = Tn + Tn+1 + Tn+2 for n >= 0.


Given `n`, return the value of Tn.


 

<strong class="example">Example 1:**



**Input:** n = 4
**Output:** 4
**Explanation:**
T_3 = 0 + 1 + 1 = 2
T_4 = 1 + 1 + 2 = 4


<strong class="example">Example 2:**



**Input:** n = 25
**Output:** 1389537


 

**Constraints:**



	- `0 <= n <= 37`
	- The answer is guaranteed to fit within a 32-bit integer, ie. `answer <= 2^31 - 1`.

---

## 🪄 Hints
> 💡 Make an array F of length 38, and set F[0] = 0, F[1] = F[2] = 1.
> 💡 Now write a loop where you set F[n+3] = F[n] + F[n+1] + F[n+2], and return F[n].

## 💻 My Solution

```cpp
class Solution {
public:
    int tribonacci(int n) {
        if (n == 0) return 0;
        if (n <= 2) return 1;

        int a = 0, b = 1, c = 1;

        for (int i = 3; i <= n; i++) {
            int d = a + b + c;
            a = b;
            b = c;
            c = d;
        }

        return c;
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
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
