<div align="center">

# 📦 474. Ones and Zeroes

*Pushed on November 03, 2026 · Problem #148 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 54.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `String` `Dynamic Programming` `Knapsack Problem` `0-1 Knapsack`

---

## 🧩 Problem Description

You are given an array of binary strings `strs` and two integers `m` and `n`.


Return *the size of the largest subset of `strs` such that there are **at most** *`m`* *`0`*&#39;s and *`n`* *`1`*&#39;s in the subset*.


A set `x` is a **subset** of a set `y` if all elements of `x` are also elements of `y`.


 

<strong class="example">Example 1:**



**Input:** strs = [&quot;10&quot;,&quot;0001&quot;,&quot;111001&quot;,&quot;1&quot;,&quot;0&quot;], m = 5, n = 3
**Output:** 4
**Explanation:** The largest subset with at most 5 0&#39;s and 3 1&#39;s is {&quot;10&quot;, &quot;0001&quot;, &quot;1&quot;, &quot;0&quot;}, so the answer is 4.
Other valid but smaller subsets include {&quot;0001&quot;, &quot;1&quot;} and {&quot;10&quot;, &quot;1&quot;, &quot;0&quot;}.
{&quot;111001&quot;} is an invalid subset because it contains 4 1&#39;s, greater than the maximum of 3.


<strong class="example">Example 2:**



**Input:** strs = [&quot;10&quot;,&quot;0&quot;,&quot;1&quot;], m = 1, n = 1
**Output:** 2
<b>Explanation:</b> The largest subset is {&quot;0&quot;, &quot;1&quot;}, so the answer is 2.


 

**Constraints:**



	- `1 <= strs.length <= 600`
	- `1 <= strs[i].length <= 100`
	- `strs[i]` consists only of digits `&#39;0&#39;` and `&#39;1&#39;`.
	- `1 <= m, n <= 100`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int findMaxForm(vector<string>& strs, int m, int n) {
        vector<vector<int>> dp(m+1,vector<int>(n+1,0));
        for(string s:strs){
            int zero=0,one=0;

            for(char c:s){
                if(c=='0')
                    zero++;
                else
                    one++;
            }
            for(int i=m;i>=zero;i--){
                for(int j=n;j>=one;j--){
                    dp[i][j]=max(dp[i][j],
                                 dp[i-zero][j-one]+1);
                }
            }
        }

        return dp[m][n];
    }
};

```

---

## 🧪 Sample Test Case

```
["10","0001","111001","1","0"]
5
3
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
