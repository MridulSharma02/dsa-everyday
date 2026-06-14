<div align="center">

# 📦 714. Best Time to Buy and Sell Stock with Transaction Fee

*Pushed on June 14, 2026 · Problem #7 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 72.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Dynamic Programming` `Greedy`

---

## 🧩 Problem Description

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i^th` day, and an integer `fee` representing a transaction fee.


Find the maximum profit you can achieve. You may complete as many transactions as you like, but you need to pay the transaction fee for each transaction.


**Note:**



	- You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before you buy again).
	- The transaction fee is only charged once for each stock purchase and sale.


 

<strong class="example">Example 1:**



**Input:** prices = [1,3,2,8,4,9], fee = 2
**Output:** 8
**Explanation:** The maximum profit can be achieved by:
- Buying at prices[0] = 1
- Selling at prices[3] = 8
- Buying at prices[4] = 4
- Selling at prices[5] = 9
The total profit is ((8 - 1) - 2) + ((9 - 4) - 2) = 8.


<strong class="example">Example 2:**



**Input:** prices = [1,3,7,5,10,3], fee = 3
**Output:** 6


 

**Constraints:**



	- `1 <= prices.length <= 5 * 10^4`
	- `1 <= prices[i] < 5 * 10^4`
	- `0 <= fee < 5 * 10^4`

---

## 🪄 Hints
> 💡 Consider the first K stock prices.  At the end, the only legal states are that you don't own a share of stock, or that you do.  Calculate the most profit you could have under each of these two cases.

## 💻 My Solution

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices, int fee) {
        int hold = -prices[0];
        int cash = 0;

        for (int i = 1; i < prices.size(); i++) {
            cash = max(cash, hold + prices[i] - fee);
            hold = max(hold, cash - prices[i]);
        }

        return cash;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,3,2,8,4,9]
2
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
