<div align="center">

# 👆 5. Longest Palindromic Substring

*Pushed on September 11, 2026 · Problem #96 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 👆 Two Pointers   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 38.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Two Pointers` `String` `Dynamic Programming` `Manacher`

---

## 🧩 Problem Description

Given a string `s`, return *the longest* <span data-keyword="palindromic-string">*palindromic*</span> <span data-keyword="substring-nonempty">*substring*</span> in `s`.


 

<strong class="example">Example 1:**



**Input:** s = &quot;babad&quot;
**Output:** &quot;bab&quot;
**Explanation:** &quot;aba&quot; is also a valid answer.


<strong class="example">Example 2:**



**Input:** s = &quot;cbbd&quot;
**Output:** &quot;bb&quot;


 

**Constraints:**



	- `1 <= s.length <= 1000`
	- `s` consist of only digits and English letters.

---

## 🪄 Hints
> 💡 How can we reuse a previously computed palindrome to compute a larger palindrome?
> 💡 If “aba” is a palindrome, is “xabax” a palindrome? Similarly is “xabay” a palindrome?

## 💻 My Solution

```python
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        if not s:
            return ""
        start = 0
        end = 0
        def expand(left, right):
            while left >= 0 and right < len(s) and s[left] == s[right]:
                left -= 1
                right += 1
            return right - left - 1  
        
        for i in range(len(s)):
            len1 = expand(i, i)      
            len2 = expand(i, i + 1)   
            max_len = max(len1, len2)
            
            if max_len > end - start:
                start = i - (max_len - 1) // 2
                end = i + max_len // 2
        
        return s[start:end + 1]
        

```

---

## 🧪 Sample Test Case

```
"babad"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Two Pointers** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying two pointers to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
