<div align="center">

# 📦 456. 132 Pattern

*Pushed on July 21, 2026 · Problem #44 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 35.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Binary Search` `Stack` `Monotonic Stack` `Ordered Set`

---

## 🧩 Problem Description

Given an array of `n` integers `nums`, a **132 pattern** is a subsequence of three integers `nums[i]`, `nums[j]` and `nums[k]` such that `i < j < k` and `nums[i] < nums[k] < nums[j]`.


Return `true`* if there is a **132 pattern** in *`nums`*, otherwise, return *`false`*.*


 

<strong class="example">Example 1:**



**Input:** nums = [1,2,3,4]
**Output:** false
**Explanation:** There is no 132 pattern in the sequence.


<strong class="example">Example 2:**



**Input:** nums = [3,1,4,2]
**Output:** true
**Explanation:** There is a 132 pattern in the sequence: [1, 4, 2].


<strong class="example">Example 3:**



**Input:** nums = [-1,3,2,0]
**Output:** true
**Explanation:** There are three 132 patterns in the sequence: [-1, 3, 2], [-1, 3, 0] and [-1, 2, 0].


 

**Constraints:**



	- `n == nums.length`
	- `1 <= n <= 2 * 10^5`
	- `-10^9 <= nums[i] <= 10^9`

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool find132pattern(vector<int>& nums) {
        int n=nums.size();
        stack<int> st;
        int second=INT_MIN;
        for(int i=n-1;i>=0;i--){
            if(nums[i]<second)
                return true;

            while(!st.empty() && nums[i]>st.top()){
                second=st.top();
                st.pop();
            }
            st.push(nums[i]);
        }

        return false;
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
> The key insight is to leverage `O(log n)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
