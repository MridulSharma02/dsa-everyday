<div align="center">

# 🔗 109. Convert Sorted List to Binary Search Tree

*Pushed on July 27, 2026 · Problem #50 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 67.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Divide and Conquer` `Tree` `Binary Search Tree` `Binary Tree`

---

## 🧩 Problem Description

Given the `head` of a singly linked list where elements are sorted in **ascending order**, convert *it to a *<span data-keyword="height-balanced">***height-balanced***</span> *binary search tree*.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/08/17/linked.jpg" style="width: 500px; height: 388px;" />

**Input:** head = [-10,-3,0,5,9]
**Output:** [0,-3,9,-10,null,5]
**Explanation:** One possible answer is [0,-3,9,-10,null,5], which represents the shown height balanced BST.


<strong class="example">Example 2:**



**Input:** head = []
**Output:** []


 

**Constraints:**



	- The number of nodes in `head` is in the range `[0, 2 * 10^4]`.
	- `-10^5 <= Node.val <= 10^5`

---

## 💻 My Solution

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
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
    TreeNode* build(ListNode* head,ListNode* tail){
        if(head==tail)
            return nullptr;

        ListNode* slow=head;
        ListNode* fast=head;
        while(fast!=tail && fast->next!=tail){
            slow=slow->next;
            fast=fast->next->next;
        }
        TreeNode* root=new TreeNode(slow->val);
        root->left=build(head,slow);
        root->right=build(slow->next,tail);

        return root;
    }
    TreeNode* sortedListToBST(ListNode* head) {
        return build(head,nullptr);
    }
};

```

---

## 🧪 Sample Test Case

```
[-10,-3,0,5,9]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Linked List** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying linked list to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
