<div align="center">

# 🔗 114. Flatten Binary Tree to Linked List

*Pushed on August 07, 2026 · Problem #61 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(V + E)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 71.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Stack` `Tree` `Depth-First Search` `Binary Tree`

---

## 🧩 Problem Description

Given the `root` of a binary tree, flatten the tree into a &quot;linked list&quot;:



	- The &quot;linked list&quot; should use the same `TreeNode` class where the `right` child pointer points to the next node in the list and the `left` child pointer is always `null`.
	- The &quot;linked list&quot; should be in the same order as a <a href="https://en.wikipedia.org/wiki/Tree_traversal#Pre-order,_NLR" target="_blank">**pre-order**** traversal**</a> of the binary tree.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/01/14/flaten.jpg" style="width: 500px; height: 226px;" />

**Input:** root = [1,2,5,3,4,null,6]
**Output:** [1,null,2,null,3,null,4,null,5,null,6]


<strong class="example">Example 2:**



**Input:** root = []
**Output:** []


<strong class="example">Example 3:**



**Input:** root = [0]
**Output:** [0]


 

**Constraints:**



	- The number of nodes in the tree is in the range `[0, 2000]`.
	- `-100 <= Node.val <= 100`


 

**Follow up:** Can you flatten the tree in-place (with `O(1)` extra space)?

---

## 🪄 Hints
> 💡 If you notice carefully in the flattened tree, each node's right child points to the next node of a pre-order traversal.

## 💻 My Solution

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    TreeNode* prev=nullptr;

    void flatten(TreeNode* root) {
        if(!root) return;
        flatten(root->right);
        flatten(root->left);

        root->right=prev;
        root->left=nullptr;
        prev=root;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,5,3,4,null,6]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Linked List** techniques.
> The key insight is to leverage `O(V + E)` time complexity
> by applying linked list to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
