<div align="center">

# 🔗 328. Odd Even Linked List

*Pushed on November 01, 2026 · Problem #147 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 62.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List`

---

## 🧩 Problem Description

Given the `head` of a singly linked list, group all the nodes with odd indices together followed by the nodes with even indices, and return *the reordered list*.


The **first** node is considered **odd**, and the **second** node is **even**, and so on.


Note that the relative order inside both the even and odd groups should remain as it was in the input.


You must solve the problem in `O(1)` extra space complexity and `O(n)` time complexity.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/03/10/oddeven-linked-list.jpg" style="width: 300px; height: 123px;" />

**Input:** head = [1,2,3,4,5]
**Output:** [1,3,5,2,4]


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/03/10/oddeven2-linked-list.jpg" style="width: 500px; height: 142px;" />

**Input:** head = [2,1,3,5,6,4,7]
**Output:** [2,3,6,7,1,5,4]


 

**Constraints:**



	- The number of nodes in the linked list is in the range `[0, 10^4]`.
	- `-10^6 <= Node.val <= 10^6`

---

## 💻 My Solution

```cpp
class Solution {
public:
    ListNode* oddEvenList(ListNode* head) {
        if (!head || !head->next) return head;

        ListNode* odd = head;
        ListNode* even = head->next;
        ListNode* evenHead = even;

        while (even && even->next) {
            odd->next = even->next;
            odd = odd->next;

            even->next = odd->next;
            even = even->next;
        }

        odd->next = evenHead;

        return head;
    }
};

```

---

## 🧪 Sample Test Case

```
[1,2,3,4,5]
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
