<div align="center">

# 🔢 29. Divide Two Integers

*Pushed on August 13, 2026 · Problem #67 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 20.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `Bit Manipulation`

---

## 🧩 Problem Description

Given two integers `dividend` and `divisor`, divide two integers **without** using multiplication, division, and mod operator.


The integer division should truncate toward zero, which means losing its fractional part. For example, `8.345` would be truncated to `8`, and `-2.7335` would be truncated to `-2`.


Return *the **quotient** after dividing *`dividend`* by *`divisor`.


**Note: **Assume we are dealing with an environment that could only store integers within the **32-bit** signed integer range: `[&minus;2^31, 2^31 &minus; 1]`. For this problem, if the quotient is **strictly greater than** `2^31 - 1`, then return `2^31 - 1`, and if the quotient is **strictly less than** `-2^31`, then return `-2^31`.


 

<strong class="example">Example 1:**



**Input:** dividend = 10, divisor = 3
**Output:** 3
**Explanation:** 10/3 = 3.33333.. which is truncated to 3.


<strong class="example">Example 2:**



**Input:** dividend = 7, divisor = -3
**Output:** -2
**Explanation:** 7/-3 = -2.33333.. which is truncated to -2.


 

**Constraints:**



	- `-2^31 <= dividend, divisor <= 2^31 - 1`
	- `divisor != 0`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int divide(int dividend, int divisor) {
        bool negative=false;
        long long dvd, div;
        if (dividend == INT_MIN && divisor == -1)
            return INT_MAX;
        if((dividend<0 && divisor>0) || (dividend>0 && divisor<0))
            negative=true;

        dvd=llabs(dividend);
        div=llabs(divisor);
        long long count=0;

        while(dvd>=div){
             int x=0;
             while(dvd>=(div<<(x+1))){
                  x++;
              }
         dvd-=(div<<x);
         count+=(1<<x);
        } 
        
        if (negative)
            return -count;

        return count;
    }
};

```

---

## 🧪 Sample Test Case

```
10
3
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
