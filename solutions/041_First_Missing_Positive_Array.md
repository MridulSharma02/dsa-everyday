<div align="center">

# 📦 41. First Missing Positive

*Pushed on August 05, 2026 · Problem #59 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 43.5%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Hash Table`

---

## 🧩 Problem Description

Given an unsorted integer array `nums`. Return the *smallest positive integer* that is *not present* in `nums`.


You must implement an algorithm that runs in `O(n)` time and uses `O(1)` auxiliary space.


 

<strong class="example">Example 1:**



**Input:** nums = [1,2,0]
**Output:** 3
**Explanation:** The numbers in the range [1,2] are all in the array.


<strong class="example">Example 2:**



**Input:** nums = [3,4,-1,1]
**Output:** 2
**Explanation:** 1 is in the array but 2 is missing.


<strong class="example">Example 3:**



**Input:** nums = [7,8,9,11,12]
**Output:** 1
**Explanation:** The smallest positive integer 1 is missing.


 

**Constraints:**



	- `1 <= nums.length <= 10^5`
	- `-2^31 <= nums[i] <= 2^31 - 1`

---

## 🪄 Hints
> 💡 Think about how you would solve the problem in non-constant space.  Can you apply that logic to the existing space?
> 💡 We don't care about duplicates or non-positive integers

## 💻 My Solution

```cpp
class Solution {
public:
    int firstMissingPositive(vector<int>& nums) {
        int n=nums.size();
        for(int i=0;i<n;i++){
            while(nums[i]>=1 && nums[i]<=n && nums[i]!=nums[nums[i]-1]){
                swap(nums[i],nums[nums[i]-1]);
            }
        }
        for(int i=0;i<n;i++){
            if(nums[i]!=i+1) return i+1;
        }

        return n+1;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,0]
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
