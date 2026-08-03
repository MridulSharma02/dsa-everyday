<div align="center">

# 📦 3336. Find the Number of Subsequences With Equal GCD

*Pushed on August 03, 2026 · Problem #57 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 66.7%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Math` `Dynamic Programming` `Number Theory` `Euclidean Algorithm` `Greatest Common Divisor`

---

## 🧩 Problem Description

You are given an integer array `nums`.


Your task is to find the number of pairs of **non-empty** <span data-keyword="subsequence-array">subsequences</span> `(seq1, seq2)` of `nums` that satisfy the following conditions:



	- The subsequences `seq1` and `seq2` are **disjoint**, meaning **no index** of `nums` is common between them.
	- The <span data-keyword="gcd-function">GCD</span> of the elements of `seq1` is equal to the GCD of the elements of `seq2`.


Return the total number of such pairs.


Since the answer may be very large, return it **modulo** `10^9 + 7`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">nums = [1,2,3,4]</span>


**Output:** <span class="example-io">10</span>


**Explanation:**


The subsequence pairs which have the GCD of their elements equal to 1 are:



	- `([**<u>1</u>**, 2, 3, 4], [1, **<u>2</u>**, **<u>3</u>**, 4])`
	- `([**<u>1</u>**, 2, 3, 4], [1, **<u>2</u>**, **<u>3</u>**, **<u>4</u>**])`
	- `([**<u>1</u>**, 2, 3, 4], [1, 2, **<u>3</u>**, **<u>4</u>**])`
	- `([**<u>1</u>**, **<u>2</u>**, 3, 4], [1, 2, **<u>3</u>**, **<u>4</u>**])`
	- `([**<u>1</u>**, 2, 3, **<u>4</u>**], [1, **<u>2</u>**, **<u>3</u>**, 4])`
	- `([1, **<u>2</u>**, **<u>3</u>**, 4], [**<u>1</u>**, 2, 3, 4])`
	- `([1, **<u>2</u>**, **<u>3</u>**, 4], [**<u>1</u>**, 2, 3, **<u>4</u>**])`
	- `([1, **<u>2</u>**, **<u>3</u>**, **<u>4</u>**], [**<u>1</u>**, 2, 3, 4])`
	- `([1, 2, **<u>3</u>**, **<u>4</u>**], [**<u>1</u>**, 2, 3, 4])`
	- `([1, 2, **<u>3</u>**, **<u>4</u>**], [**<u>1</u>**, **<u>2</u>**, 3, 4])`

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">nums = [10,20,30]</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


The subsequence pairs which have the GCD of their elements equal to 10 are:



	- `([**<u>10</u>**, 20, 30], [10, **<u>20</u>**, **<u>30</u>**])`
	- `([10, **<u>20</u>**, **<u>30</u>**], [**<u>10</u>**, 20, 30])`

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">nums = [1,1,1,1]</span>


**Output:** <span class="example-io">50</span>

</div>

 

**Constraints:**



	- `1 <= nums.length <= 200`
	- `1 <= nums[i] <= 200`

---

## 🪄 Hints
> 💡 Use dynamic programming to store number of subsequences up till index <code>i</code> with GCD <code>g1</code> and <code>g2</code>.

## 💻 My Solution

```cpp
class Solution {
public:
    static const int MOD=1e9+7;
    int dp[201][201][201];
    int dfs(int i,int g1,int g2,vector<int>& nums){
        if(i==nums.size()) return g1 && g1==g2;

        if(dp[i][g1][g2]!=-1) return dp[i][g1][g2];

        long long ans=dfs(i+1,g1,g2,nums);
        int ng1=(g1==0)?nums[i]:gcd(g1,nums[i]);
        ans+=dfs(i+1,ng1,g2,nums);

        int ng2=(g2==0)?nums[i]:gcd(g2,nums[i]);
        ans+=dfs(i+1,g1,ng2,nums);

        return dp[i][g1][g2]=ans%MOD;
    }
    int subsequencePairCount(vector<int>& nums) {
        memset(dp,-1,sizeof(dp));
        return dfs(0,0,0,nums);
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,3,4]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
