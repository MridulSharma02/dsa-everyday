<div align="center">

# 📦 55. Jump Game

*Pushed on August 29, 2026 · Problem #83 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 41.4%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Dynamic Programming` `Greedy`

---

## 🧩 Problem Description

You are given an integer array `nums`. You are initially positioned at the array&#39;s **first index**, and each element in the array represents your maximum jump length at that position.


Return `true`* if you can reach the last index, or *`false`* otherwise*.


 

<strong class="example">Example 1:**



**Input:** nums = [2,3,1,1,4]
**Output:** true
**Explanation:** Jump 1 step from index 0 to 1, then 3 steps to the last index.


<strong class="example">Example 2:**



**Input:** nums = [3,2,1,0,4]
**Output:** false
**Explanation:** You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.


 

**Constraints:**



	- `1 <= nums.length <= 10^4`
	- `0 <= nums[i] <= 10^5`

---

## 💻 My Solution

```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int maxReach=0;
        for(int i=0;i<nums.size();i++){
            if(i>maxReach)
                return false;

            maxReach=max(maxReach,i+nums[i]);
            if(maxReach>=nums.size()-1)
                return true;
        }

        return true;
    }
};

```

---

## 🧪 Sample Test Case

```
[2,3,1,1,4]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Array** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying array to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
