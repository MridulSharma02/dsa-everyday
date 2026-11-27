<div align="center">

# 🔤 2390. Removing Stars From a String

*Pushed on November 27, 2026 · Problem #172 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 80.1%              |
| **Language**         | 🔠 Python         |

**Tags:** `String` `Stack` `Simulation`

---

## 🧩 Problem Description

You are given a string `s`, which contains stars `*`.


In one operation, you can:



	- Choose a star in `s`.
	- Remove the closest **non-star** character to its **left**, as well as remove the star itself.


Return *the string after **all** stars have been removed*.


**Note:**



	- The input will be generated such that the operation is always possible.
	- It can be shown that the resulting string will always be unique.


 

<strong class="example">Example 1:**



**Input:** s = &quot;leet**cod*e&quot;
**Output:** &quot;lecoe&quot;
**Explanation:** Performing the removals from left to right:
- The closest character to the 1^st star is &#39;t&#39; in &quot;lee**<u>t</u>****cod*e&quot;. s becomes &quot;lee*cod*e&quot;.
- The closest character to the 2^nd star is &#39;e&#39; in &quot;le**<u>e</u>***cod*e&quot;. s becomes &quot;lecod*e&quot;.
- The closest character to the 3^rd star is &#39;d&#39; in &quot;leco**<u>d</u>***e&quot;. s becomes &quot;lecoe&quot;.
There are no more stars, so we return &quot;lecoe&quot;.

<strong class="example">Example 2:**



**Input:** s = &quot;erase*****&quot;
**Output:** &quot;&quot;
**Explanation:** The entire string is removed, so we return an empty string.


 

**Constraints:**



	- `1 <= s.length <= 10^5`
	- `s` consists of lowercase English letters and stars `*`.
	- The operation above can be performed on `s`.

---

## 🪄 Hints
> 💡 What data structure could we use to efficiently perform these removals?
> 💡 Use a stack to store the characters. Pop one character off the stack at each star. Otherwise, we push the character onto the stack.

## 💻 My Solution

```python
class Solution(object):
    def removeStars(self, s):
        """
        :type s: str
        :rtype: str
        """
        stack = []

        for ch in s:
            if ch == '*':
                stack.pop()
            else:
                stack.append(ch)

        return ''.join(stack)        

```

---

## 🧪 Sample Test Case

```
"leet**cod*e"
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
