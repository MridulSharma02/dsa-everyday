<div align="center">

# 📦 209. Minimum Size Subarray Sum

*Pushed on October 25, 2026 · Problem #140 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(log n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 53.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Binary Search` `Sliding Window` `Prefix Sum`

---

## 🧩 Problem Description

Given an array of positive integers `nums` and a positive integer `target`, return *the **minimal length** of a *<span data-keyword="subarray-nonempty">*subarray*</span>* whose sum is greater than or equal to* `target`. If there is no such subarray, return `0` instead.


 

<strong class="example">Example 1:**



**Input:** target = 7, nums = [2,3,1,2,4,3]
**Output:** 2
**Explanation:** The subarray [4,3] has the minimal length under the problem constraint.


<strong class="example">Example 2:**



**Input:** target = 4, nums = [1,4,4]
**Output:** 1


<strong class="example">Example 3:**



**Input:** target = 11, nums = [1,1,1,1,1,1,1,1]
**Output:** 0


 

**Constraints:**



	- `1 <= target <= 10^9`
	- `1 <= nums.length <= 10^5`
	- `1 <= nums[i] <= 10^4`


 

**Follow up:** If you have figured out the `O(n)` solution, try coding another solution of which the time complexity is `O(n log(n))`.

---

## 💻 My Solution

```cpp
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int left=0;
        int sum=0;
        int minLength=INT_MAX;
        for(int right=0;right<nums.size();right++){
            sum+=nums[right];
            while(sum>=target){
                int length=right-left+1;
                minLength=min(minLength,length);
                sum-=nums[left];
                left++;
            }
        }
        if(minLength==INT_MAX)
            return 0;

        return minLength;
    }
};

//class Solution {
//public:
//    int minSubArrayLen(int target, vector<int>& nums){
//        int minLength=INT_MAX;
//        for(int i=0;i<nums.size();i++){
//            int sum=0;
//            for(int j=i;j<nums.size();j++){
//                sum+=nums[j];
//                if (sum>=target){
//                    int length=j-i+1;
//                    minLength=min(minLength,length);
//                    break;
//                }
//            }
//        }
//        if (minLength==INT_MAX)
//            return 0;
//
//        return minLength;
//    }
//};

```

---

## 🧪 Sample Test Case

```
7
[2,3,1,2,4,3]
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
