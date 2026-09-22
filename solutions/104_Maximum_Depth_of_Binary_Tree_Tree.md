<div align="center">

# 🌳 104. Maximum Depth of Binary Tree

*Pushed on September 22, 2026 · Problem #107 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 78.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Breadth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given the `root` of a binary tree, return *its maximum depth*.


A binary tree&#39;s **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg" style="width: 400px; height: 277px;" />

**Input:** root = [3,9,20,null,null,15,7]
**Output:** 3


<strong class="example">Example 2:**



**Input:** root = [1,null,2]
**Output:** 2


 

**Constraints:**



	- The number of nodes in the tree is in the range `[0, 10^4]`.
	- `-100 <= Node.val <= 100`

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
    def maxDepth(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: int
        """
        if not root:
            return 0

        return 1 + max(self.maxDepth(root.left), self.maxDepth(root.right))

```

---

## 🧪 Sample Test Case

```
[3,9,20,null,null,15,7]
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
