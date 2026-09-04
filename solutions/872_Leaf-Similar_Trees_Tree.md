<div align="center">

# 🌳 872. Leaf-Similar Trees

*Pushed on September 04, 2026 · Problem #89 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 70.3%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Consider all the leaves of a binary tree, from left to right order, the values of those leaves form a **leaf value sequence***.*


<img alt="" src="https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/16/tree.png" style="width: 400px; height: 336px;" />


For example, in the given tree above, the leaf value sequence is `(6, 7, 4, 9, 8)`.


Two binary trees are considered *leaf-similar* if their leaf value sequence is the same.


Return `true` if and only if the two given trees with head nodes `root1` and `root2` are leaf-similar.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/09/03/leaf-similar-1.jpg" style="width: 600px; height: 237px;" />

**Input:** root1 = [3,5,1,6,2,9,8,null,null,7,4], root2 = [3,5,1,6,7,4,2,null,null,null,null,null,null,9,8]
**Output:** true


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/09/03/leaf-similar-2.jpg" style="width: 300px; height: 110px;" />

**Input:** root1 = [1,2,3], root2 = [1,3,2]
**Output:** false


 

**Constraints:**



	- The number of nodes in each tree will be in the range `[1, 200]`.
	- Both of the given trees will have values in the range `[0, 200]`.

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
    def leafSimilar(self, root1, root2):
        """
        :type root1: Optional[TreeNode]
        :type root2: Optional[TreeNode]
        :rtype: bool
        """
        def dfs(root, leaves):
            if not root:
                return

            if not root.left and not root.right:
                leaves.append(root.val)
                return

            dfs(root.left, leaves)
            dfs(root.right, leaves)

        a, b = [], []
        dfs(root1, a)
        dfs(root2, b)

        return a == b
        

```

---

## 🧪 Sample Test Case

```
[3,5,1,6,2,9,8,null,null,7,4]
[3,5,1,6,7,4,2,null,null,null,null,null,null,9,8]
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
