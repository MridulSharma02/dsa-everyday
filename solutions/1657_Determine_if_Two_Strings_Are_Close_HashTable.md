<div align="center">

# 🗂️ 1657. Determine if Two Strings Are Close

*Pushed on July 02, 2026 · Problem #25 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 54.3%              |
| **Language**         | 🔠 Python         |

**Tags:** `Hash Table` `String` `Sorting` `Counting`

---

## 🧩 Problem Description

Two strings are considered **close** if you can attain one from the other using the following operations:



	- Operation 1: Swap any two **existing** characters.

	
		- For example, `a<u>b</u>cd<u>e</u> -> a<u>e</u>cd<u>b</u>`
	
	
	- Operation 2: Transform **every** occurrence of one **existing** character into another **existing** character, and do the same with the other character.
	
		- For example, `<u>aa</u>c<u>abb</u> -> <u>bb</u>c<u>baa</u>` (all `a`&#39;s turn into `b`&#39;s, and all `b`&#39;s turn into `a`&#39;s)
	
	


You can use the operations on either string as many times as necessary.


Given two strings, `word1` and `word2`, return `true`* if *`word1`* and *`word2`* are **close**, and *`false`* otherwise.*


 

<strong class="example">Example 1:**



**Input:** word1 = &quot;abc&quot;, word2 = &quot;bca&quot;
**Output:** true
**Explanation:** You can attain word2 from word1 in 2 operations.
Apply Operation 1: &quot;a<u>bc</u>&quot; -> &quot;a<u>cb</u>&quot;
Apply Operation 1: &quot;<u>a</u>c<u>b</u>&quot; -> &quot;<u>b</u>c<u>a</u>&quot;


<strong class="example">Example 2:**



**Input:** word1 = &quot;a&quot;, word2 = &quot;aa&quot;
**Output:** false
**Explanation: **It is impossible to attain word2 from word1, or vice versa, in any number of operations.


<strong class="example">Example 3:**



**Input:** word1 = &quot;cabbba&quot;, word2 = &quot;abbccc&quot;
**Output:** true
**Explanation:** You can attain word2 from word1 in 3 operations.
Apply Operation 1: &quot;ca<u>b</u>bb<u>a</u>&quot; -> &quot;ca<u>a</u>bb<u>b</u>&quot;
Apply Operation 2: &quot;<u>c</u>aa<u>bbb</u>&quot; -> &quot;<u>b</u>aa<u>ccc</u>&quot;
Apply Operation 2: &quot;<u>baa</u>ccc&quot; -> &quot;<u>abb</u>ccc&quot;


 

**Constraints:**



	- `1 <= word1.length, word2.length <= 10^5`
	- `word1` and `word2` contain only lowercase English letters.

---

## 🪄 Hints
> 💡 Operation 1 allows you to freely reorder the string.
> 💡 Operation 2 allows you to freely reassign the letters' frequencies.

## 💻 My Solution

```python
class Solution(object):
    def closeStrings(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: bool
        """
        if len(word1) != len(word2):
            return False

        freq1 = {}
        freq2 = {}

        for c in word1:
            freq1[c] = freq1.get(c, 0) + 1

        for c in word2:
            freq2[c] = freq2.get(c, 0) + 1

        return set(freq1.keys()) == set(freq2.keys()) and \
               sorted(freq1.values()) == sorted(freq2.values())

```

---

## 🧪 Sample Test Case

```
"abc"
"bca"
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
