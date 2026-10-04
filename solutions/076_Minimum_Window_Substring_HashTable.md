<div align="center">

# 🗂️ 76. Minimum Window Substring

*Pushed on October 04, 2026 · Problem #119 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 48.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `String` `Sliding Window`

---

## 🧩 Problem Description

Given two strings `s` and `t` of lengths `m` and `n` respectively, return *the **minimum window*** <span data-keyword="substring-nonempty">***substring***</span>* of *`s`* such that every character in *`t`* (**including duplicates**) is included in the window*. If there is no such substring, return *the empty string *`&quot;&quot;`.


The testcases will be generated such that the answer is **unique**.


 

<strong class="example">Example 1:**



**Input:** s = &quot;ADOBECODEBANC&quot;, t = &quot;ABC&quot;
**Output:** &quot;BANC&quot;
**Explanation:** The minimum window substring &quot;BANC&quot; includes &#39;A&#39;, &#39;B&#39;, and &#39;C&#39; from string t.


<strong class="example">Example 2:**



**Input:** s = &quot;a&quot;, t = &quot;a&quot;
**Output:** &quot;a&quot;
**Explanation:** The entire string s is the minimum window.


<strong class="example">Example 3:**



**Input:** s = &quot;a&quot;, t = &quot;aa&quot;
**Output:** &quot;&quot;
**Explanation:** Both &#39;a&#39;s from t must be included in the window.
Since the largest window of s only has one &#39;a&#39;, return empty string.


 

**Constraints:**



	- `m == s.length`
	- `n == t.length`
	- `1 <= m, n <= 10^5`
	- `s` and `t` consist of uppercase and lowercase English letters.


 

**Follow up:** Could you find an algorithm that runs in `O(m + n)` time?

---

## 🪄 Hints
> 💡 Use two pointers to create a window of letters in s, which would have all the characters from t.
> 💡 Expand the right pointer until all the characters of t are covered.

## 💻 My Solution

```cpp
class Solution {
public:
    string minWindow(string s, string t) {
        unordered_map<char,int> need,window;

        for(char c:t) need[c]++;

        int have=0,needCount=need.size();
        int left=0,start=0,minLen=INT_MAX;

        for(int right=0;right<s.size();right++){
            char c=s[right];
            window[c]++;
            if(need.count(c) && window[c]==need[c])
                have++;
            while(have==needCount){
                if(right-left+1<minLen){
                    minLen=right-left+1;
                    start=left;
                }
                window[s[left]]--;
                if(need.count(s[left]) && window[s[left]]<need[s[left]])
                    have--;
                left++;
            }
        }

        return minLen==INT_MAX ? "" : s.substr(start,minLen);
    }
};

```

---

## 🧪 Sample Test Case

```
"ADOBECODEBANC"
"ABC"
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
