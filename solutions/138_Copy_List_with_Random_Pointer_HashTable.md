<div align="center">

# 🗂️ 138. Copy List with Random Pointer

*Pushed on November 14, 2026 · Problem #160 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 64.0%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `Linked List`

---

## 🧩 Problem Description

A linked list of length `n` is given such that each node contains an additional random pointer, which could point to any node in the list, or `null`.


Construct a <a href="https://en.wikipedia.org/wiki/Object_copying#Deep_copy" target="_blank">**deep copy**</a> of the list. The deep copy should consist of exactly `n` **brand new** nodes, where each new node has its value set to the value of its corresponding original node. Both the `next` and `random` pointer of the new nodes should point to new nodes in the copied list such that the pointers in the original list and copied list represent the same list state. **None of the pointers in the new list should point to nodes in the original list**.


For example, if there are two nodes `X` and `Y` in the original list, where `X.random --> Y`, then for the corresponding two nodes `x` and `y` in the copied list, `x.random --> y`.


Return *the head of the copied linked list*.


The linked list is represented in the input/output as a list of `n` nodes. Each node is represented as a pair of `[val, random_index]` where:



	- `val`: an integer representing `Node.val`
	- `random_index`: the index of the node (range from `0` to `n-1`) that the `random` pointer points to, or `null` if it does not point to any node.


Your code will **only** be given the `head` of the original linked list.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2019/12/18/e1.png" style="width: 700px; height: 142px;" />

**Input:** head = [[7,null],[13,0],[11,4],[10,2],[1,0]]
**Output:** [[7,null],[13,0],[11,4],[10,2],[1,0]]


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2019/12/18/e2.png" style="width: 700px; height: 114px;" />

**Input:** head = [[1,1],[2,1]]
**Output:** [[1,1],[2,1]]


<strong class="example">Example 3:**


**<img alt="" src="https://assets.leetcode.com/uploads/2019/12/18/e3.png" style="width: 700px; height: 122px;" />**



**Input:** head = [[3,null],[3,0],[3,null]]
**Output:** [[3,null],[3,0],[3,null]]


 

**Constraints:**



	- `0 <= n <= 1000`
	- `-10^4 <= Node.val <= 10^4`
	- `Node.random` is `null` or is pointing to some node in the linked list.

---

## 🪄 Hints
> 💡 Just iterate the linked list and create copies of the nodes on the go. Since a node can be referenced from multiple nodes due to the random pointers, ensure you are not making multiple copies of the same node.
> 💡 You may want to use extra space to keep old_node ---> new_node mapping to prevent creating multiple copies of the same node.

## 💻 My Solution

```cpp
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* next;
    Node* random;
    
    Node(int _val) {
        val = _val;
        next = NULL;
        random = NULL;
    }
};
*/

// Brute Force 
// class Solution {
// public:
//     Node* copyRandomList(Node* head) {
//         if(head == NULL) return NULL;

//         unordered_map<Node*, Node*> mp;

//         Node* curr = head;

//         // Create copies of all nodes
//         while(curr != NULL) {
//             mp[curr] = new Node(curr->val);
//             curr = curr->next;
//         }

//         curr = head;

//         // Connect next and random pointers
//         while(curr != NULL) {
//             mp[curr]->next = mp[curr->next];
//             mp[curr]->random = mp[curr->random];

//             curr = curr->next;
//         }

//         return mp[head];
//     }
// };

// Optimized Code without hashmap
class Solution {
public:
    Node* copyRandomList(Node* head) {
        if(head==NULL) return NULL;
        Node* curr=head;

        // Step 1: Insert copied nodes
        while(curr!=NULL) {
            Node* temp=new Node(curr->val);
            temp->next=curr->next;
            curr->next=temp;
            curr=temp->next;
        }

        // Step 2: Connect random pointers
        curr=head;
        while(curr!=NULL){
            if(curr->random!=NULL){
                curr->next->random=curr->random->next;
            }
            curr=curr->next->next;
        }

        // Step 3: Separate both lists
        curr=head;
        Node* copyHead=head->next;
        while(curr!=NULL){
            Node* copy=curr->next;
            curr->next=copy->next;
            if(copy->next!=NULL) {
                copy->next=copy->next->next;
            }
            curr=curr->next;
        }

        return copyHead;
    }
};

```

---

## 🧪 Sample Test Case

```
[[7,null],[13,0],[11,4],[10,2],[1,0]]
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Hash Table** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying hash table to efficiently reach the solution.
> Space usage is kept at `O(n)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
