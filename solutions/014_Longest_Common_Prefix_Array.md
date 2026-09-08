<div align="center">

# 📦 14. Longest Common Prefix

*Pushed on September 08, 2026 · Problem #93 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 48.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `String` `Trie`

---

## 🧩 Problem Description

Write a function to find the longest common prefix string amongst an array of strings.


If there is no common prefix, return an empty string `&quot;&quot;`.


 

<strong class="example">Example 1:**



**Input:** strs = [&quot;flower&quot;,&quot;flow&quot;,&quot;flight&quot;]
**Output:** &quot;fl&quot;


<strong class="example">Example 2:**



**Input:** strs = [&quot;dog&quot;,&quot;racecar&quot;,&quot;car&quot;]
**Output:** &quot;&quot;
**Explanation:** There is no common prefix among the input strings.


 

**Constraints:**



	- `1 <= strs.length <= 200`
	- `0 <= strs[i].length <= 200`
	- `strs[i]` consists of only lowercase English letters if it is non-empty.

---

## 💻 My Solution

```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        string ans=strs[0];
        for(int i=1;i<strs.size();i++){
            while(strs[i].find(ans)!=0){
                ans.pop_back();
                if(ans.empty()) return "";
            }
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
["flower","flow","flight"]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
