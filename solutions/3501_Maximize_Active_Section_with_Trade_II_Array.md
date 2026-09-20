<div align="center">

# 📦 3501. Maximize Active Section with Trade II

*Pushed on September 20, 2026 · Problem #105 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.6%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `String` `Binary Search` `Segment Tree`

---

## 🧩 Problem Description

You are given a binary string `s` of length `n`, where:



	- `&#39;1&#39;` represents an **active** section.
	- `&#39;0&#39;` represents an **inactive** section.


You can perform **at most one trade** to maximize the number of active sections in `s`. In a trade, you:



	- Convert a contiguous block of `&#39;1&#39;`s that is surrounded by `&#39;0&#39;`s to all `&#39;0&#39;`s.
	- Afterward, convert a contiguous block of `&#39;0&#39;`s that is surrounded by `&#39;1&#39;`s to all `&#39;1&#39;`s.


Additionally, you are given a **2D array** `queries`, where `queries[i] = [li, ri]` represents a <span data-keyword="substring-nonempty">substring</span> `s[li...ri]`.


For each query, determine the **maximum** possible number of active sections in `s` after making the optimal trade on the substring `s[li...ri]`.


Return an array `answer`, where `answer[i]` is the result for `queries[i]`.


**Note**



	- For each query, treat `s[li...ri]` as if it is **augmented** with a `&#39;1&#39;` at both ends, forming `t = &#39;1&#39; + s[li...ri] + &#39;1&#39;`. The augmented `&#39;1&#39;`s **do not** contribute to the final count.
	- The queries are independent of each other.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;01&quot;, queries = [[0,1]]</span>


**Output:** <span class="example-io">[1]</span>


**Explanation:**


Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 1.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;0100&quot;, queries = [[0,3],[0,2],[1,3],[2,3]]</span>


**Output:** <span class="example-io">[4,3,1,1]</span>


**Explanation:**



	- 
	Query `[0, 3]` &rarr; Substring `&quot;0100&quot;` &rarr; Augmented to `&quot;101001&quot;`<br />
	Choose `&quot;0100&quot;`, convert `&quot;0100&quot;` &rarr; `&quot;0000&quot;` &rarr; `&quot;1111&quot;`.<br />
	The final string without augmentation is `&quot;1111&quot;`. The maximum number of active sections is 4.

	
	- 
	Query `[0, 2]` &rarr; Substring `&quot;010&quot;` &rarr; Augmented to `&quot;10101&quot;`<br />
	Choose `&quot;010&quot;`, convert `&quot;010&quot;` &rarr; `&quot;000&quot;` &rarr; `&quot;111&quot;`.<br />
	The final string without augmentation is `&quot;1110&quot;`. The maximum number of active sections is 3.

	
	- 
	Query `[1, 3]` &rarr; Substring `&quot;100&quot;` &rarr; Augmented to `&quot;11001&quot;`<br />
	Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 1.

	
	- 
	Query `[2, 3]` &rarr; Substring `&quot;00&quot;` &rarr; Augmented to `&quot;1001&quot;`<br />
	Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 1.

	

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;1000100&quot;, queries = [[1,5],[0,6],[0,4]]</span>


**Output:** <span class="example-io">[6,7,2]</span>


**Explanation:**



	<li data-end="383" data-start="217">
	<p data-end="383" data-start="219">Query `[1, 5]` &rarr; Substring <code data-end="255" data-start="246">&quot;00010&quot;` &rarr; Augmented to <code data-end="282" data-start="271">&quot;1000101&quot;`<br data-end="285" data-start="282" />
	Choose <code data-end="303" data-start="294">&quot;00010&quot;`, convert <code data-end="322" data-start="313">&quot;00010&quot;` &rarr; <code data-end="322" data-start="313">&quot;00000&quot;` &rarr; <code data-end="334" data-start="325">&quot;11111&quot;`.<br />
	The final string without augmentation is <code data-end="404" data-start="396">&quot;1111110&quot;`. The maximum number of active sections is 6.

	
	<li data-end="561" data-start="385">
	<p data-end="561" data-start="387">Query `[0, 6]` &rarr; Substring <code data-end="425" data-start="414">&quot;1000100&quot;` &rarr; Augmented to <code data-end="454" data-start="441">&quot;110001001&quot;`<br data-end="457" data-start="454" />
	Choose <code data-end="477" data-start="466">&quot;000100&quot;`, convert <code data-end="498" data-start="487">&quot;000100&quot;` &rarr; <code data-end="498" data-start="487">&quot;000000&quot;` &rarr; <code data-end="512" data-start="501">&quot;111111&quot;`.<br />
	The final string without augmentation is <code data-end="404" data-start="396">&quot;1111111&quot;`. The maximum number of active sections is 7.

	
	<li data-end="741" data-start="563">
	<p data-end="741" data-start="565">Query `[0, 4]` &rarr; Substring <code data-end="601" data-start="592">&quot;10001&quot;` &rarr; Augmented to <code data-end="627" data-start="617">&quot;1100011&quot;`<br data-end="630" data-start="627" />
	Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 2.

	

</div>

<strong class="example">Example 4:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;01010&quot;, queries = [[0,3],[1,4],[1,3]]</span>


**Output:** <span class="example-io">[4,4,2]</span>


**Explanation:**



	- 
	Query `[0, 3]` &rarr; Substring `&quot;0101&quot;` &rarr; Augmented to `&quot;101011&quot;`<br />
	Choose `&quot;010&quot;`, convert `&quot;010&quot;` &rarr; `&quot;000&quot;` &rarr; `&quot;111&quot;`.<br />
	The final string without augmentation is `&quot;11110&quot;`. The maximum number of active sections is 4.

	
	- 
	Query `[1, 4]` &rarr; Substring `&quot;1010&quot;` &rarr; Augmented to `&quot;110101&quot;`<br />
	Choose `&quot;010&quot;`, convert `&quot;010&quot;` &rarr; `&quot;000&quot;` &rarr; `&quot;111&quot;`.<br />
	The final string without augmentation is `&quot;01111&quot;`. The maximum number of active sections is 4.

	
	- 
	Query `[1, 3]` &rarr; Substring `&quot;101&quot;` &rarr; Augmented to `&quot;11011&quot;`<br />
	Because there is no block of `&#39;1&#39;`s surrounded by `&#39;0&#39;`s, no valid trade is possible. The maximum number of active sections is 2.

	

</div>

 

**Constraints:**



	- `1 <= n == s.length <= 10^5`
	- `1 <= queries.length <= 10^5`
	- `s[i]` is either `&#39;0&#39;` or `&#39;1&#39;`.
	- `queries[i] = [li, ri]`
	- `0 <= li <= ri < n`

---

## 🪄 Hints
> 💡 Split consecutive zeros and ones into segments and give each segment an ID.
> 💡 The answer should be the maximum of <code>ans[i] = len[i - 1] + len[i + 1]</code>, where <code>i</code> is a one-segment.

## 💻 My Solution

```cpp
class Solution {
public:
    int solve(string sub) {
        int ones = 0;
        for (char c : sub)
            if (c == '1')
                ones++;

        string t = "1" + sub + "1";
        vector<pair<char, int>> blocks;
        for (int i = 0; i < t.size();) {
            int j = i;
            while (j < t.size() && t[j] == t[i])
                j++;

            blocks.push_back({t[i], j - i});
            i = j;
        }

        int ans = ones;
        for (int i = 1; i + 1 < blocks.size(); i++) {
            if (blocks[i].first == '1' &&
                blocks[i - 1].first == '0' &&
                blocks[i + 1].first == '0') {

                ans = max(ans,
                          ones + blocks[i - 1].second + blocks[i + 1].second);
            }
        }

        return ans;
    }

    vector<int> maxActiveSectionsAfterTrade(string s, vector<vector<int>>& queries) {
        int n = s.size();
        // Prefix sum of active sections ('1')
        vector<int> pref(n + 1, 0);
        for (int i = 0; i < n; i++)
            pref[i + 1] = pref[i] + (s[i] == '1');

        int totalOnes = pref[n];
        vector<int> ans;
        for (auto &q : queries) {
            int l = q[0];
            int r = q[1];
            int onesInSub = pref[r + 1] - pref[l];
            int outsideOnes = totalOnes - onesInSub;

            string sub = s.substr(l, r - l + 1);
            ans.push_back(outsideOnes + solve(sub));
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
"01"
[[0,1]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(log n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
