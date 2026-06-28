<div align="center">

# 📦 739. Daily Temperatures

*Pushed on June 28, 2026 · Problem #21 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 68.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Stack` `Monotonic Stack`

---

## 🧩 Problem Description

Given an array of integers `temperatures` represents the daily temperatures, return *an array* `answer` *such that* `answer[i]` *is the number of days you have to wait after the* `i^th` *day to get a warmer temperature*. If there is no future day for which this is possible, keep `answer[i] == 0` instead.


 

<strong class="example">Example 1:**

**Input:** temperatures = [73,74,75,71,69,72,76,73]
**Output:** [1,1,4,2,1,1,0,0]
<strong class="example">Example 2:**

**Input:** temperatures = [30,40,50,60]
**Output:** [1,1,1,0]
<strong class="example">Example 3:**

**Input:** temperatures = [30,60,90]
**Output:** [1,1,0]

 

**Constraints:**



	- `1 <= temperatures.length <= 10^5`
	- `30 <= temperatures[i] <= 100`

---

## 🪄 Hints
> 💡 If the temperature is say, 70 today, then in the future a warmer temperature must be either 71, 72, 73, ..., 99, or 100.  We could remember when all of them occur next.

## 💻 My Solution

```cpp
class Solution {
public:
    vector<int> dailyTemperatures(vector<int>& temperatures) {
        int n = temperatures.size();
        vector<int> ans(n, 0);
        stack<int> st;

        for (int i = 0; i < n; i++) {
            while (!st.empty() && temperatures[i] > temperatures[st.top()]) {
                int idx = st.top();
                st.pop();
                ans[idx] = i - idx;
            }
            st.push(i);
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[73,74,75,71,69,72,76,73]
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
