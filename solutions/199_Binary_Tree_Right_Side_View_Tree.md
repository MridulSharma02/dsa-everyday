<div align="center">

# 🌳 199. Binary Tree Right Side View

*Pushed on July 07, 2026 · Problem #30 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 70.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Breadth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given the `root` of a binary tree, imagine yourself standing on the **right side** of it, return *the values of the nodes you can see ordered from top to bottom*.


 

<strong class="example">Example 1:**


<div class="example-block">
**Input:** <span class="example-io">root = [1,2,3,null,5,null,4]</span>


**Output:** <span class="example-io">[1,3,4]</span>


**Explanation:**


<img alt="" src="https://assets.leetcode.com/uploads/2024/11/24/tmpd5jn43fs-1.png" style="width: 400px; height: 207px;" />

</div>

<strong class="example">Example 2:**


<div class="example-block">
**Input:** <span class="example-io">root = [1,2,3,4,null,null,null,5]</span>


**Output:** <span class="example-io">[1,3,4,5]</span>


**Explanation:**


<img alt="" src="https://assets.leetcode.com/uploads/2024/11/24/tmpkpe40xeh-1.png" style="width: 400px; height: 214px;" />

</div>

<strong class="example">Example 3:**


<div class="example-block">
**Input:** <span class="example-io">root = [1,null,3]</span>


**Output:** <span class="example-io">[1,3]</span>

</div>

<strong class="example">Example 4:**


<div class="example-block">
**Input:** <span class="example-io">root = []</span>


**Output:** <span class="example-io">[]</span>

</div>

 

**Constraints:**



	- The number of nodes in the tree is in the range `[0, 100]`.
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
from collections import deque

class Solution(object):
    def rightSideView(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        if not root:
            return []

        ans = []
        q = deque([root])

        while q:
            size = len(q)

            for i in range(size):
                node = q.popleft()

                if i == size - 1:
                    ans.append(node.val)

                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)

        return ans
        

```

---

## 🧪 Sample Test Case

```
[1,2,3,null,5,null,4]
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
