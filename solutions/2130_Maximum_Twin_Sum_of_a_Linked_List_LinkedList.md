<div align="center">

# 🔗 2130. Maximum Twin Sum of a Linked List

*Pushed on September 26, 2026 · Problem #111 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 83.3%              |
| **Language**         | 🔠 C++         |

**Tags:** `Linked List` `Two Pointers` `Stack`

---

## 🧩 Problem Description

In a linked list of size `n`, where `n` is **even**, the `i^th` node (**0-indexed**) of the linked list is known as the **twin** of the `(n-1-i)^th` node, if `0 <= i <= (n / 2) - 1`.



	- For example, if `n = 4`, then node `0` is the twin of node `3`, and node `1` is the twin of node `2`. These are the only nodes with twins for `n = 4`.


The **twin sum **is defined as the sum of a node and its twin.


Given the `head` of a linked list with even length, return *the **maximum twin sum** of the linked list*.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg1drawio.png" style="width: 250px; height: 70px;" />

**Input:** head = [5,4,2,1]
**Output:** 6
**Explanation:**
Nodes 0 and 1 are the twins of nodes 3 and 2, respectively. All have twin sum = 6.
There are no other nodes with twins in the linked list.
Thus, the maximum twin sum of the linked list is 6. 


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg2drawio.png" style="width: 250px; height: 70px;" />

**Input:** head = [4,2,2,3]
**Output:** 7
**Explanation:**
The nodes with twins present in this linked list are:
- Node 0 is the twin of node 3 having a twin sum of 4 + 3 = 7.
- Node 1 is the twin of node 2 having a twin sum of 2 + 2 = 4.
Thus, the maximum twin sum of the linked list is max(7, 4) = 7. 


<strong class="example">Example 3:**

<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg3drawio.png" style="width: 200px; height: 88px;" />

**Input:** head = [1,100000]
**Output:** 100001
**Explanation:**
There is only one node with a twin in the linked list having twin sum of 1 + 100000 = 100001.


 

**Constraints:**



	- The number of nodes in the list is an **even** integer in the range `[2, 10^5]`.
	- `1 <= Node.val <= 10^5`

---

## 🪄 Hints
> 💡 How can "reversing" a part of the linked list help find the answer?
> 💡 We know that the nodes of the first half are twins of nodes in the second half, so try dividing the linked list in half and reverse the second half.

## 💻 My Solution

```cpp
class Solution {
public:
    int pairSum(ListNode* head) {
        ListNode* slow = head;
        ListNode* fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        ListNode* prev = nullptr;
        while (slow) {
            ListNode* nxt = slow->next;
            slow->next = prev;
            prev = slow;
            slow = nxt;
        }

        int ans = 0;
        while (prev) {
            ans = max(ans, head->val + prev->val);
            head = head->next;
            prev = prev->next;
        }

        return ans;
    }
};

```

---

## 🧪 Sample Test Case

```
[5,4,2,1]
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
