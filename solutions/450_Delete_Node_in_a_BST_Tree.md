<div align="center">

# 🌳 450. Delete Node in a BST

*Pushed on July 10, 2026 · Problem #33 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🌳 Tree   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 55.0%              |
| **Language**         | 🔠 Python         |

**Tags:** `Tree` `Binary Search Tree` `Binary Tree`

---

## 🧩 Problem Description

Given a root node reference of a BST and a key, delete the node with the given key in the BST. Return *the **root node reference** (possibly updated) of the BST*.


Basically, the deletion can be divided into two stages:



	- Search for a node to remove.
	- If the node is found, delete the node.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/09/04/del_node_1.jpg" style="width: 800px; height: 214px;" />

**Input:** root = [5,3,6,2,4,null,7], key = 3
**Output:** [5,4,6,2,null,null,7]
**Explanation:** Given key to delete is 3. So we find the node with value 3 and delete it.
One valid answer is [5,4,6,2,null,null,7], shown in the above BST.
Please notice that another valid answer is [5,2,6,null,4,null,7] and it&#39;s also accepted.
<img alt="" src="https://assets.leetcode.com/uploads/2020/09/04/del_node_supp.jpg" style="width: 350px; height: 255px;" />


<strong class="example">Example 2:**



**Input:** root = [5,3,6,2,4,null,7], key = 0
**Output:** [5,3,6,2,4,null,7]
**Explanation:** The tree does not contain a node with value = 0.


<strong class="example">Example 3:**



**Input:** root = [], key = 0
**Output:** []


 

**Constraints:**



	- The number of nodes in the tree is in the range `[0, 10^4]`.
	- `-10^5 <= Node.val <= 10^5`
	- Each node has a **unique** value.
	- `root` is a valid binary search tree.
	- `-10^5 <= key <= 10^5`


 

**Follow up:** Could you solve it with time complexity `O(height of tree)`?

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
    def deleteNode(self, root, key):
        """
        :type root: TreeNode
        :type key: int
        :rtype: TreeNode
        """
        if not root:
            return None

        if key < root.val:
            root.left = self.deleteNode(root.left, key)
        elif key > root.val:
            root.right = self.deleteNode(root.right, key)
        else:
            if not root.left:
                return root.right
            if not root.right:
                return root.left

            temp = root.right
            while temp.left:
                temp = temp.left

            root.val = temp.val
            root.right = self.deleteNode(root.right, temp.val)

        return root
        

```

---

## 🧪 Sample Test Case

```
[5,3,6,2,4,null,7]
3
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Tree** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying tree to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
