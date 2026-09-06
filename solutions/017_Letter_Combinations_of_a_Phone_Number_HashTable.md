<div align="center">

# 🗂️ 17. Letter Combinations of a Phone Number

*Pushed on September 06, 2026 · Problem #91 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 66.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `String` `Backtracking`

---

## 🧩 Problem Description

Given a string containing digits from `2-9` inclusive, return all possible letter combinations that the number could represent. Return the answer in **any order**.


A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

<img alt="" src="https://assets.leetcode.com/uploads/2022/03/15/1200px-telephone-keypad2svg.png" style="width: 300px; height: 243px;" />
 

<strong class="example">Example 1:**



**Input:** digits = &quot;23&quot;
**Output:** [&quot;ad&quot;,&quot;ae&quot;,&quot;af&quot;,&quot;bd&quot;,&quot;be&quot;,&quot;bf&quot;,&quot;cd&quot;,&quot;ce&quot;,&quot;cf&quot;]


<strong class="example">Example 2:**



**Input:** digits = &quot;2&quot;
**Output:** [&quot;a&quot;,&quot;b&quot;,&quot;c&quot;]


 

**Constraints:**



	- `1 <= digits.length <= 4`
	- `digits[i]` is a digit in the range `[&#39;2&#39;, &#39;9&#39;]`.

---

## 💻 My Solution

```cpp
class Solution {
public:
    vector<string> ans;
    vector<string> mp = {
        "", "", "abc", "def", "ghi",
        "jkl", "mno", "pqrs", "tuv", "wxyz"
    };

    void backtrack(string& digits, int idx, string curr) {
        if (idx == digits.size()) {
            ans.push_back(curr);
            return;
        }

        for (char ch : mp[digits[idx] - '0']) {
            backtrack(digits, idx + 1, curr + ch);
        }
    }

    vector<string> letterCombinations(string digits) {
        if (digits.empty()) return {};

        backtrack(digits, 0, "");
        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"23"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Hash Table** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying hash table to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
