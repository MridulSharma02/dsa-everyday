<div align="center">

# 🔤 3499. Maximize Active Section with Trade I

*Pushed on September 19, 2026 · Problem #104 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 60.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Enumeration`

---

## 🧩 Problem Description

You are given a binary string `s` of length `n`, where:



	- `&#39;1&#39;` represents an **active** section.
	- `&#39;0&#39;` represents an **inactive** section.


You can perform **at most one trade** to maximize the number of active sections in `s`. In a trade, you:



	- Convert a contiguous block of `&#39;1&#39;`s that is surrounded by `&#39;0&#39;`s to all `&#39;0&#39;`s.
	- Afterward, convert a contiguous block of `&#39;0&#39;`s that is surrounded by `&#39;1&#39;`s to all `&#39;1&#39;`s.


Return the **maximum** number of active sections in `s` after making the optimal trade.


**Note:** Treat `s` as if it is **augmented** with a `&#39;1&#39;` at both ends, forming `t = &#39;1&#39; + s + &#39;1&#39;`. The augmented `&#39;1&#39;`s **do not** contribute to the final count.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;01&quot;</span>


**Output:** <span class="example-io">1</span>


**Explanation:**


Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 1.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;0100&quot;</span>


**Output:** <span class="example-io">4</span>


**Explanation:**



	- String `&quot;0100&quot;` &rarr; Augmented to `&quot;101001&quot;`.
	- Choose `&quot;0100&quot;`, convert `&quot;10<u>**1**</u>001&quot;` &rarr; `&quot;1<u>**0000**</u>1&quot;` &rarr; `&quot;1<u>**1111**</u>1&quot;`.
	- The final string without augmentation is `&quot;1111&quot;`. The maximum number of active sections is 4.

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;1000100&quot;</span>


**Output:** <span class="example-io">7</span>


**Explanation:**



	- String `&quot;1000100&quot;` &rarr; Augmented to `&quot;110001001&quot;`.
	- Choose `&quot;000100&quot;`, convert `&quot;11000<u>**1**</u>001&quot;` &rarr; `&quot;11<u>**000000**</u>1&quot;` &rarr; `&quot;11<u>**111111**</u>1&quot;`.
	- The final string without augmentation is `&quot;1111111&quot;`. The maximum number of active sections is 7.

</div>

<strong class="example">Example 4:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;01010&quot;</span>


**Output:** <span class="example-io">4</span>


**Explanation:**



	- String `&quot;01010&quot;` &rarr; Augmented to `&quot;1010101&quot;`.
	- Choose `&quot;010&quot;`, convert `&quot;10<u>**1**</u>0101&quot;` &rarr; `&quot;1<u>**000**</u>101&quot;` &rarr; `&quot;1<u>**111**</u>101&quot;`.
	- The final string without augmentation is `&quot;11110&quot;`. The maximum number of active sections is 4.

</div>

 

**Constraints:**



	- `1 <= n == s.length <= 10^5`
	- `s[i]` is either `&#39;0&#39;` or `&#39;1&#39;`

---

## 🪄 Hints
> 💡 Split the string into several zero-one segments.
> 💡 For each one-segment, if it has two neighbors (i.e., it is surrounded by two zero-segments), the total sum of their lengths is one of the candidates for <code>delta</code>.

## 💻 My Solution

```cpp
class Solution {
public:
    int maxActiveSectionsAfterTrade(string s) {
        int ones = 0;
        for(char c : s)
            if(c == '1')
                ones++;

        string t = "1" + s + "1";
        vector<pair<char,int>> blocks;
        for(int i = 0; i < t.size();) {
            int j = i;
            while(j < t.size() && t[j] == t[i]) j++;
            blocks.push_back({t[i], j - i});
            i = j;
        }

        int ans = ones;
        for(int i = 1; i + 1 < blocks.size(); i++) {
            if(blocks[i].first == '1' &&
               blocks[i-1].first == '0' &&
               blocks[i+1].first == '0') {

                ans = max(ans,ones + blocks[i-1].second + blocks[i+1].second);
            }
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"01"
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
