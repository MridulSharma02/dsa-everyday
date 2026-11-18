<div align="center">

# 🔗 86. Partition List

*Pushed on November 18, 2026 · Problem #163 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 62.5%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Two Pointers`

---

## 🧩 Problem Description

Given the `head` of a linked list and a value `x`, partition it such that all nodes **less than** `x` come before nodes **greater than or equal** to `x`.


You should **preserve** the original relative order of the nodes in each of the two partitions.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/01/04/partition.jpg" style="width: 662px; height: 222px;" />

**Input:** head = [1,4,3,2,5,2], x = 3
**Output:** [1,2,2,4,3,5]


<strong class="example">Example 2:**



**Input:** head = [2,1], x = 2
**Output:** [1,2]


 

**Constraints:**



	- The number of nodes in the list is in the range `[0, 200]`.
	- `-100 <= Node.val <= 100`
	- `-200 <= x <= 200`

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
    ListNode* partition(ListNode* head, int x) {
        ListNode small(0),large(0);
        ListNode* s=&small;
        ListNode* l=&large;

        while(head!=NULL){
            if(head->val<x){
                s->next=head;
                s=s->next;
            }
            else{
                l->next=head;
                l=l->next;
            }
            head=head->next;
        }
        l->next=NULL;
        s->next=large.next;

        return small.next;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,4,3,2,5,2]
3
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
