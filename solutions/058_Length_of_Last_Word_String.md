<div align="center">

# 🔤 58. Length of Last Word

*Pushed on September 05, 2026 · Problem #90 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 59.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `String`

---

## 🧩 Problem Description

Given a string `s` consisting of words and spaces, return *the length of the **last** word in the string.*


A **word** is a maximal <span data-keyword="substring-nonempty">substring</span> consisting of non-space characters only.


 

<strong class="example">Example 1:**



**Input:** s = &quot;Hello World&quot;
**Output:** 5
**Explanation:** The last word is &quot;World&quot; with length 5.


<strong class="example">Example 2:**



**Input:** s = &quot;   fly me   to   the moon  &quot;
**Output:** 4
**Explanation:** The last word is &quot;moon&quot; with length 4.


<strong class="example">Example 3:**



**Input:** s = &quot;luffy is still joyboy&quot;
**Output:** 6
**Explanation:** The last word is &quot;joyboy&quot; with length 6.


 

**Constraints:**



	- `1 <= s.length <= 10^4`
	- `s` consists of only English letters and spaces `&#39; &#39;`.
	- There will be at least one word in `s`.

---

## 💻 My Solution

```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        int i=s.size()-1;
        while(i>=0 && s[i]==' ') i--;

        int len=0;
        while(i>=0 && s[i]!=' '){
            len++;
            i--;
        }

        return len;
    }
};

```

---

## 🧪 Sample Test Case

```
"Hello World"
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
