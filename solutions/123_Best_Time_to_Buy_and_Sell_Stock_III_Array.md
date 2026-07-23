<div align="center">

# 📦 123. Best Time to Buy and Sell Stock III

*Pushed on July 23, 2026 · Problem #46 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 54.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Dynamic Programming`

---

## 🧩 Problem Description

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i^th` day.


Find the maximum profit you can achieve. You may complete **at most two transactions**.


**Note:** You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before you buy again).


 

<strong class="example">Example 1:**



**Input:** prices = [3,3,5,0,0,3,1,4]
**Output:** 6
**Explanation:** Buy on day 4 (price = 0) and sell on day 6 (price = 3), profit = 3-0 = 3.
Then buy on day 7 (price = 1) and sell on day 8 (price = 4), profit = 4-1 = 3.

<strong class="example">Example 2:**



**Input:** prices = [1,2,3,4,5]
**Output:** 4
**Explanation:** Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Note that you cannot buy on day 1, buy on day 2 and sell them later, as you are engaging multiple transactions at the same time. You must sell before buying again.


<strong class="example">Example 3:**



**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transaction is done, i.e. max profit = 0.


 

**Constraints:**



	- `1 <= prices.length <= 10^5`
	- `0 <= prices[i] <= 10^5`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int buy1=INT_MIN,buy2=INT_MIN;
        int sell1=0,sell2=0;
        
        for(int price:prices){
            buy1=max(buy1,-price);
            sell1=max(sell1,buy1+price);
            buy2=max(buy2,sell1-price);
            sell2=max(sell2,buy2+price);
        }

        return sell2;
    }
};

```

---

## 🧪 Sample Test Case

```
[3,3,5,0,0,3,1,4]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
