<div align="center">

# 📦 268. Missing Number

*Pushed on October 06, 2026 · Problem #120 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 72.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Hash Table` `Math` `Binary Search` `Bit Manipulation` `Sorting`

---

## 🧩 Problem Description

Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return *the only number in the range that is missing from the array.*


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">nums = [3,0,1]</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


`n = 3` since there are 3 numbers, so all numbers are in the range `[0,3]`. 2 is the missing number in the range since it does not appear in `nums`.

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">nums = [0,1]</span>


**Output:** <span class="example-io">2</span>


**Explanation:**


`n = 2` since there are 2 numbers, so all numbers are in the range `[0,2]`. 2 is the missing number in the range since it does not appear in `nums`.

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">nums = [9,6,4,2,3,5,7,0,1]</span>


**Output:** <span class="example-io">8</span>


**Explanation:**


`n = 9` since there are 9 numbers, so all numbers are in the range `[0,9]`. 8 is the missing number in the range since it does not appear in `nums`.

</div>

<div class="simple-translate-system-theme" id="simple-translate">
<div>
<div class="simple-translate-button isShow" style="background-image: url(&quot;moz-extension://8a9ffb6b-7e69-4e93-aae1-436a1448eff6/icons/512.png&quot;); height: 22px; width: 22px; top: 318px; left: 36px;"> </div>

<div class="simple-translate-panel " style="width: 300px; height: 200px; top: 0px; left: 0px; font-size: 13px;">
<div class="simple-translate-result-wrapper" style="overflow: hidden;">
<div class="simple-translate-move" draggable="true"> </div>

<div class="simple-translate-result-contents">
<p class="simple-translate-result" dir="auto"> 


<p class="simple-translate-candidate" dir="auto"> 

</div>
</div>
</div>
</div>
</div>

 

**Constraints:**



	- `n == nums.length`
	- `1 <= n <= 10^4`
	- `0 <= nums[i] <= n`
	- All the numbers of `nums` are **unique**.


 

**Follow up:** Could you implement a solution using only `O(1)` extra space complexity and `O(n)` runtime complexity?

---

## 💻 My Solution

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        int total=n*(n+1)/2;
        int sum=0;
        for(int x:nums)
            sum+=x;

        return total-sum;
    }
};

```

---

## 🧪 Sample Test Case

```
[3,0,1]
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
