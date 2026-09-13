<div align="center">

# 🗂️ 3. Longest Substring Without Repeating Characters

*Pushed on September 13, 2026 · Problem #98 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 40.0%              |
| **Language**         | 🔠 Python         |

**Tags:** `Hash Table` `String` `Sliding Window`

---

## 🧩 Problem Description

Given a string `s`, find the length of the **longest** <span data-keyword="substring-nonempty">**substring**</span> without duplicate characters.


 

<strong class="example">Example 1:**



**Input:** s = &quot;abcabcbb&quot;
**Output:** 3
**Explanation:** The answer is &quot;abc&quot;, with the length of 3. Note that `&quot;bca&quot;` and `&quot;cab&quot;` are also correct answers.


<strong class="example">Example 2:**



**Input:** s = &quot;bbbbb&quot;
**Output:** 1
**Explanation:** The answer is &quot;b&quot;, with the length of 1.


<strong class="example">Example 3:**



**Input:** s = &quot;pwwkew&quot;
**Output:** 3
**Explanation:** The answer is &quot;wke&quot;, with the length of 3.
Notice that the answer must be a substring, &quot;pwke&quot; is a subsequence and not a substring.


 

**Constraints:**



	- `0 <= s.length <= 10^5`
	- `s` consists of English letters, digits, symbols and spaces.

---

## 🪄 Hints
> 💡 There are less than 100 unique characters. We can check all substrings with length at most 100 for example. This is a good enough approximation.

## 💻 My Solution

```python
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        char_set = set()
        left = 0
        max_length = 0
        
        for right in range(len(s)):
            while s[right] in char_set:
                char_set.remove(s[left])
                left += 1
            
            char_set.add(s[right])
            max_length = max(max_length, right - left + 1)
        
        return max_length
        

```

---

## 🧪 Sample Test Case

```
"abcabcbb"
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
