<div align="center">

# 🔤 394. Decode String

*Pushed on July 09, 2026 · Problem #32 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 62.9%              |
| **Language**         | 🔠 Python         |

**Tags:** `String` `Stack` `Recursion`

---

## 🧩 Problem Description

Given an encoded string, return its decoded string.


The encoding rule is: `k[encoded_string]`, where the `encoded_string` inside the square brackets is being repeated exactly `k` times. Note that `k` is guaranteed to be a positive integer.


You may assume that the input string is always valid; there are no extra white spaces, square brackets are well-formed, etc. Furthermore, you may assume that the original data does not contain any digits and that digits are only for those repeat numbers, `k`. For example, there will not be input like `3a` or `2[4]`.


The test cases are generated so that the length of the output will never exceed `10^5`.


 

<strong class="example">Example 1:**



**Input:** s = &quot;3[a]2[bc]&quot;
**Output:** &quot;aaabcbc&quot;


<strong class="example">Example 2:**



**Input:** s = &quot;3[a2[c]]&quot;
**Output:** &quot;accaccacc&quot;


<strong class="example">Example 3:**



**Input:** s = &quot;2[abc]3[cd]ef&quot;
**Output:** &quot;abcabccdcdcdef&quot;


 

**Constraints:**



	- `1 <= s.length <= 30`
	- `s` consists of lowercase English letters, digits, and square brackets `&#39;[]&#39;`.
	- `s` is guaranteed to be **a valid** input.
	- All the integers in `s` are in the range `[1, 300]`.

---

## 💻 My Solution

```python
class Solution(object):
    def decodeString(self, s):
        """
        :type s: str
        :rtype: str
        """
        st = []
        curr = ""
        num = 0

        for ch in s:
            if ch.isdigit():
                num = num * 10 + int(ch)
            elif ch == "[":
                st.append((curr, num))
                curr = ""
                num = 0
            elif ch == "]":
                prev, repeat = st.pop()
                curr = prev + curr * repeat
            else:
                curr += ch

        return curr   

```

---

## 🧪 Sample Test Case

```
"3[a]2[bc]"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
