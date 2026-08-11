<div align="center">

# 🔁 401. Binary Watch

*Pushed on August 11, 2026 · Problem #65 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔁 Backtracking   |
| **Time Complexity**  | ⏱️ `O(1)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 66.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Backtracking` `Bit Manipulation`

---

## 🧩 Problem Description

A binary watch has 4 LEDs on the top to represent the hours (0-11), and 6 LEDs on the bottom to represent the minutes (0-59). Each LED represents a zero or one, with the least significant bit on the right.



	- For example, the below binary watch reads `&quot;4:51&quot;`.


<img alt="" src="https://assets.leetcode.com/uploads/2021/04/08/binarywatch.jpg" style="width: 500px; height: 500px;" />


Given an integer `turnedOn` which represents the number of LEDs that are currently on (ignoring the PM), return *all possible times the watch could represent*. You may return the answer in **any order**.


The hour must not contain a leading zero.



	- For example, `&quot;01:00&quot;` is not valid. It should be `&quot;1:00&quot;`.


The minute must consist of two digits and may contain a leading zero.



	- For example, `&quot;10:2&quot;` is not valid. It should be `&quot;10:02&quot;`.


 

<strong class="example">Example 1:**

**Input:** turnedOn = 1
**Output:** ["0:01","0:02","0:04","0:08","0:16","0:32","1:00","2:00","4:00","8:00"]
<strong class="example">Example 2:**

**Input:** turnedOn = 9
**Output:** []

 

**Constraints:**



	- `0 <= turnedOn <= 10`

---

## 🪄 Hints
> 💡 Simplify by seeking for solutions that involve comparing set bit counts.
> 💡 Consider precomputing all possible times for comparison.

## 💻 My Solution

```cpp
class Solution {
public:
    int bits(int n){
        int count=0;
        while(n>0){
            if(n&1)
                count++;
            n=n>>1;
        }

        return count;
    }

    vector<string> readBinaryWatch(int turnedOn) {

        vector<string> ans;

        for(int h=0;h<=11;h++){
            for(int m=0;m<=59;m++){
                if(bits(h) + bits(m) == turnedOn){
                    if (m<10)
                        ans.push_back(to_string(h) + ":0" + to_string(m));
                    else
                        ans.push_back(to_string(h) + ":" + to_string(m));
                }
            }
        }

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

> This problem primarily involves **Backtracking** techniques.
> The key insight is to leverage `O(1)` time complexity
> by applying backtracking to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
