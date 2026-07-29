<div align="center">

# 🔢 168. Excel Sheet Column Title

*Pushed on July 29, 2026 · Problem #52 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 47.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Math` `String`

---

## 🧩 Problem Description

Given an integer `columnNumber`, return *its corresponding column title as it appears in an Excel sheet*.


For example:



A -> 1
B -> 2
C -> 3
...
Z -> 26
AA -> 27
AB -> 28 
...


 

<strong class="example">Example 1:**



**Input:** columnNumber = 1
**Output:** &quot;A&quot;


<strong class="example">Example 2:**



**Input:** columnNumber = 28
**Output:** &quot;AB&quot;


<strong class="example">Example 3:**



**Input:** columnNumber = 701
**Output:** &quot;ZY&quot;


 

**Constraints:**



	- `1 <= columnNumber <= 2^31 - 1`

---

## 💻 My Solution

```cpp
class Solution {
public:
    string convertToTitle(int columnNumber) {
        string ans;

        while(columnNumber){
            columnNumber--;
            ans.push_back('A'+columnNumber%26);
            columnNumber/=26;
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
1
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
