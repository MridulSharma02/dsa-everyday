<div align="center">

# 🔗 23. Merge k Sorted Lists

*Pushed on September 29, 2026 · Problem #114 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🔴 Hard |
| **Topic**            | 🔗 Linked List   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 60.6%              |
| **Language**         | 🔠 Python         |

**Tags:** `Linked List` `Divide and Conquer` `Heap (Priority Queue)` `Merge Sort` `Tournament Sort`

---

## 🧩 Problem Description

You are given an array of `k` linked-lists `lists`, each linked-list is sorted in ascending order.


*Merge all the linked-lists into one sorted linked-list and return it.*


 

<strong class="example">Example 1:**



**Input:** lists = [[1,4,5],[1,3,4],[2,6]]
**Output:** [1,1,2,3,4,4,5,6]
**Explanation:** The linked-lists are:
[
  1->4->5,
  1->3->4,
  2->6
]
merging them into one sorted linked list:
1->1->2->3->4->4->5->6


<strong class="example">Example 2:**



**Input:** lists = []
**Output:** []


<strong class="example">Example 3:**



**Input:** lists = [[]]
**Output:** []


 

**Constraints:**



	- `k == lists.length`
	- `0 <= k <= 10^4`
	- `0 <= lists[i].length <= 500`
	- `-10^4 <= lists[i][j] <= 10^4`
	- `lists[i]` is sorted in **ascending order**.
	- The sum of `lists[i].length` will not exceed `10^4`.

---

## 💻 My Solution

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def mergeKLists(self, lists):
        """
        :type lists: List[Optional[ListNode]]
        :rtype: Optional[ListNode]
        """
        if not lists:
            return None

        while len(lists)>1:
            merged=[]

            for i in range(0,len(lists),2):
                l1=lists[i]
                l2=lists[i+1] if i+1<len(lists) else None
                merged.append(self.merge(l1,l2))

            lists=merged

        return lists[0]

    def merge(self,l1,l2):
        dummy=ListNode(0)
        cur=dummy

        while l1 and l2:
            if l1.val<l2.val:
                cur.next=l1
                l1=l1.next
            else:
                cur.next=l2
                l2=l2.next
            cur=cur.next

        cur.next=l1 or l2
        return dummy.next       

```

---

## 🧪 Sample Test Case

```
[[1,4,5],[1,3,4],[2,6]]
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
