<div align="center">

# 🧬 1372. Longest ZigZag Path in a Binary Tree

*Pushed on September 14, 2026 · Problem #99 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🧬 Dynamic Programming   |
| **Time Complexity**  | ⏱️ `O(n²)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 67.4%              |
| **Language**         | 🔠 Python         |

**Tags:** `Dynamic Programming` `Tree` `Depth-First Search` `Binary Tree` `DP on Trees`

---

## 🧩 Problem Description

You are given the `root` of a binary tree.


A ZigZag path for a binary tree is defined as follow:



	- Choose **any **node in the binary tree and a direction (right or left).
	- If the current direction is right, move to the right child of the current node; otherwise, move to the left child.
	- Change the direction from right to left or from left to right.
	- Repeat the second and third steps until you can&#39;t move in the tree.


Zigzag length is defined as the number of nodes visited - 1. (A single node has a length of 0).


Return *the longest **ZigZag** path contained in that tree*.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/01/22/sample_1_1702.png" style="width: 221px; height: 383px;" />

**Input:** root = [1,null,1,1,1,null,null,1,1,null,1,null,null,null,1]
**Output:** 3
**Explanation:** Longest ZigZag path in blue nodes (right -> left -> right).


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/01/22/sample_2_1702.png" style="width: 157px; height: 329px;" />

**Input:** root = [1,1,1,null,1,null,null,1,1,null,1]
**Output:** 4
**Explanation:** Longest ZigZag path in blue nodes (left -> right -> left -> right).


<strong class="example">Example 3:**



**Input:** root = [1]
**Output:** 0


 

**Constraints:**



	- The number of nodes in the tree is in the range `[1, 5 * 10^4]`.
	- `1 <= Node.val <= 100`

---

## 🪄 Hints
> 💡 Create this function maxZigZag(node, direction) maximum zigzag given a node and direction (right or left).

## 💻 My Solution

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def longestZigZag(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        self.ans = 0

        def dfs(node, left, right):
            if not node:
                return

            self.ans = max(self.ans, left, right)

            dfs(node.left, right + 1, 0)
            dfs(node.right, 0, left + 1)

        dfs(root, 0, 0)
        return self.ans
        

```

---

## 🧪 Sample Test Case

```
[1,null,1,1,1,null,null,1,1,null,1,null,null,null,1]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Dynamic Programming** techniques.
> The key insight is to leverage `O(n²)` time complexity
> by applying dynamic programming to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
