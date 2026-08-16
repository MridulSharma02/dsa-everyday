<div align="center">

# 🔢 1071. Greatest Common Divisor of Strings

*Pushed on August 16, 2026 · Problem #70 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🔢 Math   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 54.3%              |
| **Language**         | 🔠 Python         |

**Tags:** `Math` `String` `Euclidean Algorithm` `Greatest Common Divisor`

---

## 🧩 Problem Description

For two strings `s` and `t`, we say &quot;`t` divides `s`&quot; if and only if `s = t + t + t + ... + t + t` (i.e., `t` is concatenated with itself one or more times).


Given two strings `str1` and `str2`, return *the largest string *`x`* such that *`x`* divides both *`str1`* and *`str2`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">str1 = &quot;ABCABC&quot;, str2 = &quot;ABC&quot;</span>


**Output:** <span class="example-io">&quot;ABC&quot;</span>

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">str1 = &quot;ABABAB&quot;, str2 = &quot;ABAB&quot;</span>


**Output:** <span class="example-io">&quot;AB&quot;</span>

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">str1 = &quot;LEET&quot;, str2 = &quot;CODE&quot;</span>


**Output:** <span class="example-io">&quot;&quot;</span>

</div>

<strong class="example">Example 4:**


<div class="example-block">
**Input:** <span class="example-io">str1 = &quot;AAAAAB&quot;, str2 = &quot;AAA&quot;</span>


**Output:** <span class="example-io">&quot;&quot;</span>​​​​​​​

</div>

 

**Constraints:**



	- `1 <= str1.length, str2.length <= 1000`
	- `str1` and `str2` consist of English uppercase letters.

---

## 🪄 Hints
> 💡 The greatest common divisor must be a prefix of each string, so we can try all prefixes.

## 💻 My Solution

```python
class Solution(object):
    def gcdOfStrings(self, str1, str2):
        """
        :type str1: str
        :type str2: str
        :rtype: str
        """

        if str1 + str2 != str2 + str1:
            return ""

        a = len(str1)
        b = len(str2)

        while b:
            a, b = b, a % b

        return str1[:a]

```

---

## 🧪 Sample Test Case

```
"ABCABC"
"ABC"
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
