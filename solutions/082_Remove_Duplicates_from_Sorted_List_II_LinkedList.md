<div align="center">

# 🔗 82. Remove Duplicates from Sorted List II

*Pushed on November 25, 2026 · Problem #170 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 52.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Two Pointers`

---

## 🧩 Problem Description

You are given the `head` of a **sorted** linked list.


Delete all nodes that have **duplicate** numbers, leaving only **distinct** numbers from the original list.


Return the linked list **sorted** as well.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/01/04/linkedlist1.jpg" style="width: 500px; height: 142px;" />

**Input:** head = [1,2,3,3,4,4,5]
**Output:** [1,2,5]


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/01/04/linkedlist2.jpg" style="width: 500px; height: 205px;" />

**Input:** head = [1,1,1,2,3]
**Output:** [2,3]


 

**Constraints:**



	- The number of nodes in the list is in the range `[0, 300]`.
	- `-100 <= Node.val <= 100`
	- The list is guaranteed to be **sorted** in ascending order.

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
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode dummy(0);
        dummy.next=head;
        ListNode* prev=&dummy;
        ListNode* curr=head;
        while(curr!=NULL){
            if(curr->next!=NULL && curr->val==curr->next->val){
                int value=curr->val;
                while(curr!=NULL && curr->val==value){
                    curr=curr->next;
                }
                prev->next=curr;
            }
            else{
                prev=curr;
                curr=curr->next;
            }
        }

        return dummy.next;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,3,3,4,4,5]
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
