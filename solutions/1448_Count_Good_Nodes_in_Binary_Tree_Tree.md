<div align="center">

# 🌳 1448. Count Good Nodes in Binary Tree

*Pushed on July 08, 2026 · Problem #31 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 73.9%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Breadth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given a binary tree `root`, a node *X* in the tree is named **good** if in the path from root to *X* there are no nodes with a value *greater than* X.


Return the number of **good** nodes in the binary tree.


 

<strong class="example">Example 1:**


**<img alt="" src="https://assets.leetcode.com/uploads/2020/04/02/test_sample_1.png" style="width: 263px; height: 156px;" />**



**Input:** root = [3,1,4,3,null,1,5]
**Output:** 4
**Explanation:** Nodes in blue are **good**.
Root Node (3) is always a good node.
Node 4 -> (3,4) is the maximum value in the path starting from the root.
Node 5 -> (3,4,5) is the maximum value in the path
Node 3 -> (3,1,3) is the maximum value in the path.

<strong class="example">Example 2:**


**<img alt="" src="https://assets.leetcode.com/uploads/2020/04/02/test_sample_2.png" style="width: 157px; height: 161px;" />**



**Input:** root = [3,3,null,4,2]
**Output:** 3
**Explanation:** Node 2 -> (3, 3, 2) is not good, because &quot;3&quot; is higher than it.

<strong class="example">Example 3:**



**Input:** root = [1]
**Output:** 1
**Explanation:** Root is considered as **good**.

 

**Constraints:**



	- The number of nodes in the binary tree is in the range `[1, 10^5]`.
	- Each node&#39;s value is between `[-10^4, 10^4]`.

---

## 🪄 Hints
> 💡 Use DFS (Depth First Search) to traverse the tree, and constantly keep track of the current path maximum.

## 💻 My Solution

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def goodNodes(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        def dfs(node, mx):
            if not node:
                return 0

            count = 0
            if node.val >= mx:
                count = 1
                mx = node.val

            return count + dfs(node.left, mx) + dfs(node.right, mx)

        return dfs(root, float("-inf"))
        

```

---

## 🧪 Sample Test Case

```
[3,1,4,3,null,1,5]
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
