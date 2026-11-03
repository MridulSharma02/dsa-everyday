<div align="center">

# 📚 901. Online Stock Span

*Pushed on November 03, 2026 · Problem #149 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📚 Stack   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 70.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Stack` `Design` `Monotonic Stack` `Data Stream`

---

## 🧩 Problem Description

Design an algorithm that collects daily price quotes for some stock and returns **the span** of that stock&#39;s price for the current day.


The **span** of the stock&#39;s price in one day is the maximum number of consecutive days (starting from that day and going backward) for which the stock price was less than or equal to the price of that day.



	- For example, if the prices of the stock in the last four days are `[7,2,1,2]` and the price of the stock today is 2, then the span of today is 4 because starting from today, the price of the stock was less than or equal to 2 for 4 consecutive days.
	- Also, if the prices of the stock in the last four days is `[7,34,1,2]` and the price of the stock today is `8`, then the span of today is `3` because starting from today, the price of the stock was less than or equal `8` for `3` consecutive days.


Implement the `StockSpanner` class:



	- `StockSpanner()` Initializes the object of the class.
	- `int next(int price)` Returns the **span** of the stock&#39;s price given that today&#39;s price is `price`.


 

<strong class="example">Example 1:**



**Input**
[&quot;StockSpanner&quot;, &quot;next&quot;, &quot;next&quot;, &quot;next&quot;, &quot;next&quot;, &quot;next&quot;, &quot;next&quot;, &quot;next&quot;]
[[], [100], [80], [60], [70], [60], [75], [85]]
**Output**
[null, 1, 1, 1, 2, 1, 4, 6]

**Explanation**
StockSpanner stockSpanner = new StockSpanner();
stockSpanner.next(100); // return 1
stockSpanner.next(80);  // return 1
stockSpanner.next(60);  // return 1
stockSpanner.next(70);  // return 2
stockSpanner.next(60);  // return 1
stockSpanner.next(75);  // return 4, because the last 4 prices (including today&#39;s price of 75) were less than or equal to today&#39;s price.
stockSpanner.next(85);  // return 6


 

**Constraints:**



	- `1 <= price <= 10^5`
	- At most `10^4` calls will be made to `next`.

---

## 💻 My Solution

```cpp
class StockSpanner {
public:
    stack<pair<int,int>> st;

    StockSpanner() {
    }

    int next(int price) {
        int span = 1;

        while (!st.empty() && st.top().first <= price) {
            span += st.top().second;
            st.pop();
        }

        st.push({price, span});
        return span;
    }
};

/**
 * Your StockSpanner object will be instantiated and called as such:
 * StockSpanner* obj = new StockSpanner();
 * int param_1 = obj->next(price);
 */

```

---

## 🧪 Sample Test Case

```
["StockSpanner","next","next","next","next","next","next","next"]
[[],[100],[80],[60],[70],[60],[75],[85]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Stack** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying stack to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
