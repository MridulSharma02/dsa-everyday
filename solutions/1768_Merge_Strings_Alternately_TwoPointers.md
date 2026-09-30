<div align="center">

# 👆 1768. Merge Strings Alternately

*Pushed on September 30, 2026 · Problem #115 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 👆 Two Pointers   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 82.2%              |
| **Language**         | 🔠 Python         |

**Tags:** `Two Pointers` `String`

---

## 🧩 Problem Description

You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.


Return *the merged string.*


 

<strong class="example">Example 1:**



**Input:** word1 = &quot;abc&quot;, word2 = &quot;pqr&quot;
**Output:** &quot;apbqcr&quot;
**Explanation:** The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r


<strong class="example">Example 2:**



**Input:** word1 = &quot;ab&quot;, word2 = &quot;pqrs&quot;
**Output:** &quot;apbqrs&quot;
**Explanation:** Notice that as word2 is longer, &quot;rs&quot; is appended to the end.
word1:  a   b 
word2:    p   q   r   s
merged: a p b q   r   s


<strong class="example">Example 3:**



**Input:** word1 = &quot;abcd&quot;, word2 = &quot;pq&quot;
**Output:** &quot;apbqcd&quot;
**Explanation:** Notice that as word1 is longer, &quot;cd&quot; is appended to the end.
word1:  a   b   c   d
word2:    p   q 
merged: a p b q c   d


 

**Constraints:**



	- `1 <= word1.length, word2.length <= 100`
	- `word1` and `word2` consist of lowercase English letters.

---

## 🪄 Hints
> 💡 Use two pointers, one pointer for each string. Alternately choose the character from each pointer, and move the pointer upwards.

## 💻 My Solution

```python
class Solution(object):
    def mergeAlternately(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: str
        """
        a=len(word1)
        b=len(word2)
        c=""
        if a<b:
            for i in range(a):
                c+=word1[i]
                c+=word2[i]
            c+=word2[a:]
        elif a>b:
            for i in range(b):
                c+=word1[i]
                c+=word2[i]
            c+=word1[b:]
        else :
            for i in range(a):
                c+=word1[i]
                c+=word2[i]
        return c


```

---

## 🧪 Sample Test Case

```
"abc"
"pqr"
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
