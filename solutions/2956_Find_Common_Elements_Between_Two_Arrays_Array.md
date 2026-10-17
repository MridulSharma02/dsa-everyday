<div align="center">

# 📦 2956. Find Common Elements Between Two Arrays

*Pushed on October 17, 2026 · Problem #132 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 📦 Array   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 84.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Array` `Hash Table`

---

## 🧩 Problem Description

You are given two integer arrays `nums1` and `nums2` of sizes `n` and `m`, respectively. Calculate the following values:



	- `answer1` : the number of indices `i` such that `nums1[i]` exists in `nums2`.
	- `answer2` : the number of indices `i` such that `nums2[i]` exists in `nums1`.


Return `[answer1,answer2]`.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">nums1 = [2,3,2], nums2 = [1,2]</span>


**Output:** <span class="example-io">[2,1]</span>


**Explanation:**


<img src="https://assets.leetcode.com/uploads/2024/05/26/3488_find_common_elements_between_two_arrays-t1.gif" style="width: 225px; height: 150px;" />

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">nums1 = [4,3,2,3,1], nums2 = [2,2,5,2,3,6]</span>


**Output:** <span class="example-io">[3,4]</span>


**Explanation:**


The elements at indices 1, 2, and 3 in `nums1` exist in `nums2` as well. So `answer1` is 3.


The elements at indices 0, 1, 3, and 4 in `nums2` exist in `nums1`. So `answer2` is 4.

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">nums1 = [3,4,2,3], nums2 = [1,5]</span>


**Output:** <span class="example-io">[0,0]</span>


**Explanation:**


No numbers are common between `nums1` and `nums2`, so answer is [0,0].

</div>

 

**Constraints:**



	- `n == nums1.length`
	- `m == nums2.length`
	- `1 <= n, m <= 100`
	- `1 <= nums1[i], nums2[i] <= 100`

---

## 🪄 Hints
> 💡 Since the constraints are small, you can use brute force to solve the problem.
> 💡 For each element <code>i</code> in <code>nums1</code>, iterate over all elements of <code>nums2</code> to find if it occurs.

## 💻 My Solution

```cpp
class Solution {
public:
    vector<int> findIntersectionValues(vector<int>& nums1, vector<int>& nums2) {
        int answer1=0;
        int answer2=0;
        for(int i=0;i<nums1.size();i++){
            for(int j=0;j<nums2.size();j++){
                if(nums1[i]==nums2[j]){
                    answer1++;
                    break;
                }
            }
        }
        for(int i=0;i<nums2.size();i++){
            for(int j=0;j<nums1.size();j++){
                if(nums2[i]==nums1[j]){
                    answer2++;
                    break;
                }
            }
        }

        return {answer1,answer2};
    }
};

```

---

## 🧪 Sample Test Case

```
[2,3,2]
[1,2]
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
