<div align="center">

# 🌳 437. Path Sum III

*Pushed on November 05, 2026 · Problem #151 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 46.8%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given the `root` of a binary tree and an integer `targetSum`, return *the number of paths where the sum of the values along the path equals* `targetSum`.


The path does not need to start or end at the root or a leaf, but it must go downwards (i.e., traveling only from parent nodes to child nodes).


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/04/09/pathsum3-1-tree.jpg" style="width: 450px; height: 386px;" />

**Input:** root = [10,5,-3,3,2,null,11,3,-2,null,1], targetSum = 8
**Output:** 3
**Explanation:** The paths that sum to 8 are shown.


<strong class="example">Example 2:**



**Input:** root = [5,4,8,11,null,13,4,7,2,null,null,5,1], targetSum = 22
**Output:** 3


 

**Constraints:**



	- The number of nodes in the tree is in the range `[0, 1000]`.
	- `-10^9 <= Node.val <= 10^9`
	- `-1000 <= targetSum <= 1000`

---

## 💻 My Solution

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def pathSum(self, root, targetSum):
        """
        :type root: TreeNode
        :type targetSum: int
        :rtype: int
        """
        prefix = {0: 1}

        def dfs(node, curr):
            if not node:
                return 0

            curr += node.val
            ans = prefix.get(curr - targetSum, 0)

            prefix[curr] = prefix.get(curr, 0) + 1

            ans += dfs(node.left, curr)
            ans += dfs(node.right, curr)

            prefix[curr] -= 1

            return ans

        return dfs(root, 0)
        

```

---

## 🧪 Sample Test Case

```
[10,5,-3,3,2,null,11,3,-2,null,1]
8
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Tree** techniques.
> The key insight is to leverage `O(V + E)` time complexity
> by applying tree to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
