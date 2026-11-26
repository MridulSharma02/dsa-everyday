<div align="center">

# 🔗 19. Remove Nth Node From End of List

*Pushed on November 26, 2026 · Problem #171 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 53.1%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Two Pointers`

---

## 🧩 Problem Description

Given the `head` of a linked list, remove the `n^th` node from the end of the list and return its head.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg" style="width: 542px; height: 222px;" />

**Input:** head = [1,2,3,4,5], n = 2
**Output:** [1,2,3,5]


<strong class="example">Example 2:**



**Input:** head = [1], n = 1
**Output:** []


<strong class="example">Example 3:**



**Input:** head = [1,2], n = 1
**Output:** [1]


 

**Constraints:**



	- The number of nodes in the list is `sz`.
	- `1 <= sz <= 30`
	- `0 <= Node.val <= 100`
	- `1 <= n <= sz`


 

**Follow up:** Could you do this in one pass?

---

## 🪄 Hints
> 💡 Maintain two pointers and update one with a delay of n steps.

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
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* dummy=new ListNode(0);
        dummy->next=head;
        ListNode* fast=dummy;
        ListNode* slow=dummy;

        for(int i=0;i<=n;i++)
            fast=fast->next;
        while(fast){
            fast=fast->next;
            slow=slow->next;
        }
        slow->next=slow->next->next;

        return dummy->next;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,3,4,5]
2
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
