<div align="center">

# 🔗 2. Add Two Numbers

*Pushed on June 09, 2026 · Problem #2 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(√n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 48.6%              |
| **Language**         | 🔠 C         |

**Tags:** `Linked List` `Math` `Recursion`

---

## 🧩 Problem Description

You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order**, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.


You may assume the two numbers do not contain any leading zero, except the number 0 itself.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/10/02/addtwonumber1.jpg" style="width: 483px; height: 342px;" />

**Input:** l1 = [2,4,3], l2 = [5,6,4]
**Output:** [7,0,8]
**Explanation:** 342 + 465 = 807.


<strong class="example">Example 2:**



**Input:** l1 = [0], l2 = [0]
**Output:** [0]


<strong class="example">Example 3:**



**Input:** l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
**Output:** [8,9,9,9,0,0,0,1]


 

**Constraints:**



	- The number of nodes in each linked list is in the range `[1, 100]`.
	- `0 <= Node.val <= 9`
	- It is guaranteed that the list represents a number that does not have leading zeros.

---

## 💻 My Solution

```c
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    struct ListNode dummy;
    struct ListNode *tail = &dummy;
    dummy.next = NULL;

    int carry = 0;

    while (l1 || l2 || carry) {
        int sum = carry;

        if (l1) {
            sum += l1->val;
            l1 = l1->next;
        }

        if (l2) {
            sum += l2->val;
            l2 = l2->next;
        }

        tail->next = malloc(sizeof(struct ListNode));
        tail = tail->next;
        tail->val = sum % 10;
        tail->next = NULL;

        carry = sum / 10;
    }

    return dummy.next;
}

```

---

## 🧪 Sample Test Case

```
[2,4,3]
[5,6,4]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Linked List** techniques.
> The key insight is to leverage `O(√n)` time complexity
> by applying linked list to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
