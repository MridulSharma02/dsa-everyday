<div align="center">

# 🔤 520. Detect Capital

*Pushed on October 16, 2026 · Problem #131 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 57.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `String`

---

## 🧩 Problem Description

We define the usage of capitals in a word to be right when one of the following cases holds:



	- All letters in this word are capitals, like `&quot;USA&quot;`.
	- All letters in this word are not capitals, like `&quot;leetcode&quot;`.
	- Only the first letter in this word is capital, like `&quot;Google&quot;`.


Given a string `word`, return `true` if the usage of capitals in it is right.


 

<strong class="example">Example 1:**

**Input:** word = "USA"
**Output:** true
<strong class="example">Example 2:**

**Input:** word = "FlaG"
**Output:** false

 

**Constraints:**



	- `1 <= word.length <= 100`
	- `word` consists of lowercase and uppercase English letters.

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool detectCapitalUse(string word) {
        int count=0;
        for(int i=0;i<word.size();i++){
            if(isupper(word[i]))
                count++;
        }
        if(count==word.size())
            return true;
        if(count==0)
            return true;
        if(count==1 && isupper(word[0]))
            return true;

        return false;
    }
};

```

---

## 🧪 Sample Test Case

```
"USA"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
