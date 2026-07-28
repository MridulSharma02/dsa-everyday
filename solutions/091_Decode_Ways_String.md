<div align="center">

# 🔤 91. Decode Ways

*Pushed on July 28, 2026 · Problem #51 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔤 String   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 38.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `String` `Dynamic Programming`

---

## 🧩 Problem Description

You have intercepted a secret message encoded as a string of numbers. The message is **decoded** via the following mapping:


`&quot;1&quot; -> &#39;A&#39;<br />
&quot;2&quot; -> &#39;B&#39;<br />
...<br />
&quot;25&quot; -> &#39;Y&#39;<br />
&quot;26&quot; -> &#39;Z&#39;`


However, while decoding the message, you realize that there are many different ways you can decode the message because some codes are contained in other codes (`&quot;2&quot;` and `&quot;5&quot;` vs `&quot;25&quot;`).


For example, `&quot;11106&quot;` can be decoded into:



	- `&quot;AAJF&quot;` with the grouping `(1, 1, 10, 6)`
	- `&quot;KJF&quot;` with the grouping `(11, 10, 6)`
	- The grouping `(1, 11, 06)` is invalid because `&quot;06&quot;` is not a valid code (only `&quot;6&quot;` is valid).


Note: there may be strings that are impossible to decode.<br />
<br />
Given a string s containing only digits, return the **number of ways** to **decode** it. If the entire string cannot be decoded in any valid way, return `0`.


The test cases are generated so that the answer fits in a **32-bit** integer.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;12&quot;</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


&quot;12&quot; could be decoded as &quot;AB&quot; (1 2) or &quot;L&quot; (12).

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;226&quot;</span>


**Output:** <span class="example-io">3</span>


**Explanation:**


&quot;226&quot; could be decoded as &quot;BZ&quot; (2 26), &quot;VF&quot; (22 6), or &quot;BBF&quot; (2 2 6).

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">s = &quot;06&quot;</span>


**Output:** <span class="example-io">0</span>


**Explanation:**


&quot;06&quot; cannot be mapped to &quot;F&quot; because of the leading zero (&quot;6&quot; is different from &quot;06&quot;). In this case, the string is not a valid encoding, so return 0.

</div>

 

**Constraints:**



	- `1 <= s.length <= 100`
	- `s` contains only digits and may contain leading zero(s).

---

## 💻 My Solution

```cpp
class Solution {
public:
    int numDecodings(string s) {
        int n=s.size();
        vector<int> dp(n+1,0);
        dp[0]=1;
        dp[1]=s[0]=='0' ? 0 : 1;
        for(int i=2;i<=n;i++){
            if(s[i-1]!='0')
                dp[i]+=dp[i-1];

            int two=(s[i-2]-'0')*10+(s[i-1]-'0');
            if(two>=10 && two<=26)
                dp[i]+=dp[i-2];
        }

        return dp[n];
    }
};

```

---

## 🧪 Sample Test Case

```
"12"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **String** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying string to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
