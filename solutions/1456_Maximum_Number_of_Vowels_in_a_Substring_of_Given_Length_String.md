<div align="center">

# 🔤 1456. Maximum Number of Vowels in a Substring of Given Length

*Pushed on September 24, 2026 · Problem #109 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 63.0%              |
| **Language**         | 🔠 Python         |

**Tags:** `String` `Sliding Window`

---

## 🧩 Problem Description

Given a string `s` and an integer `k`, return *the maximum number of vowel letters in any substring of *`s`* with length *`k`.


**Vowel letters** in English are `&#39;a&#39;`, `&#39;e&#39;`, `&#39;i&#39;`, `&#39;o&#39;`, and `&#39;u&#39;`.


 

<strong class="example">Example 1:**



**Input:** s = &quot;abciiidef&quot;, k = 3
**Output:** 3
**Explanation:** The substring &quot;iii&quot; contains 3 vowel letters.


<strong class="example">Example 2:**



**Input:** s = &quot;aeiou&quot;, k = 2
**Output:** 2
**Explanation:** Any substring of length 2 contains 2 vowels.


<strong class="example">Example 3:**



**Input:** s = &quot;leetcode&quot;, k = 3
**Output:** 2
**Explanation:** &quot;lee&quot;, &quot;eet&quot; and &quot;ode&quot; contain 2 vowels.


 

**Constraints:**



	- `1 <= s.length <= 10^5`
	- `s` consists of lowercase English letters.
	- `1 <= k <= s.length`

---

## 🪄 Hints
> 💡 Keep a window of size k and maintain the number of vowels in it.
> 💡 Keep moving the window and update the number of vowels while moving. Answer is max number of vowels of any window.

## 💻 My Solution

```python
class Solution(object):
    def maxVowels(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: int
        """
        a=0
        for i in range(k):
            if s[i] in "aeiou":
                a+=1
        m = a
        for i in range(k,len(s)):
            if s[i-k] in "aeiou":
                a-=1
            if s[i] in "aeiou":
                a+=1
            if a>m:
                m=a

        return m

```

---

## 🧪 Sample Test Case

```
"abciiidef"
3
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
