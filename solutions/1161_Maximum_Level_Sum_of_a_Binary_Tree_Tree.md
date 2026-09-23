<div align="center">

# 🌳 1161. Maximum Level Sum of a Binary Tree

*Pushed on September 23, 2026 · Problem #108 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 70.0%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Depth-First Search` `Breadth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given the `root` of a binary tree, the level of its root is `1`, the level of its children is `2`, and so on.


Return the **smallest** level `x` such that the sum of all the values of nodes at level `x` is **maximal**.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2019/05/03/capture.JPG" style="width: 200px; height: 175px;" />

**Input:** root = [1,7,0,7,-8,null,null]
**Output:** 2
**Explanation: **
Level 1 sum = 1.
Level 2 sum = 7 + 0 = 7.
Level 3 sum = 7 + -8 = -1.
So we return the level with the maximum sum which is level 2.


<strong class="example">Example 2:**



**Input:** root = [989,null,10250,98693,-89388,null,null,null,-32127]
**Output:** 2


 

**Constraints:**



	- The number of nodes in the tree is in the range `[1, 10^4]`.
	- `-10^5 <= Node.val <= 10^5`

---

## 🪄 Hints
> 💡 Calculate the sum for each level then find the level with the maximum sum.
> 💡 How can you traverse the tree ?

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
    def maxLevelSum(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        q = deque([root])
        level = 1
        ans = 1
        mx = float("-inf")

        while q:
            s = 0

            for _ in range(len(q)):
                node = q.popleft()
                s += node.val

                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)

            if s > mx:
                mx = s
                ans = level

            level += 1

        return ans
        

```

---

## 🧪 Sample Test Case

```
[1,7,0,7,-8,null,null]
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
