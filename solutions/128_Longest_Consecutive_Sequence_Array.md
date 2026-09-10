<div align="center">

# 📦 128. Longest Consecutive Sequence

*Pushed on September 10, 2026 · Problem #95 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 47.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Hash Table` `Union-Find`

---

## 🧩 Problem Description

Given an unsorted array of integers `nums`, return *the length of the longest consecutive elements sequence.*


You must write an algorithm that runs in `O(n)` time.


 

<strong class="example">Example 1:**



**Input:** nums = [100,4,200,1,3,2]
**Output:** 4
**Explanation:** The longest consecutive elements sequence is `[1, 2, 3, 4]`. Therefore its length is 4.


<strong class="example">Example 2:**



**Input:** nums = [0,3,7,2,5,8,4,6,0,1]
**Output:** 9


<strong class="example">Example 3:**



**Input:** nums = [1,0,1,2]
**Output:** 3


 

**Constraints:**



	- `0 <= nums.length <= 10^5`
	- `-10^9 <= nums[i] <= 10^9`

---

## 💻 My Solution

```cpp
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        unordered_set<int> st(nums.begin(),nums.end());
        int ans=0;
        for(int num:st){
            if(st.count(num-1)) continue;

            int curr=num;
            int len=1;

            while(st.count(curr+1)){
                curr++;
                len++;
            }
            ans=max(ans,len);
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[100,4,200,1,3,2]
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
