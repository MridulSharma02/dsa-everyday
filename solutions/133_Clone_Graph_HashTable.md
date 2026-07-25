<div align="center">

# 🗂️ 133. Clone Graph

*Pushed on July 25, 2026 · Problem #48 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 65.8%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `Depth-First Search` `Breadth-First Search` `Graph Theory`

---

## 🧩 Problem Description

Given a reference of a node in a **<a href="https://en.wikipedia.org/wiki/Connectivity_(graph_theory)#Connected_graph" target="_blank">connected</a>** undirected graph.


Return a <a href="https://en.wikipedia.org/wiki/Object_copying#Deep_copy" target="_blank">**deep copy**</a> (clone) of the graph.


Each node in the graph contains a value (`int`) and a list (`List[Node]`) of its neighbors.



class Node {
    public int val;
    public List<Node> neighbors;
}


 


**Test case format:**


For simplicity, each node&#39;s value is the same as the node&#39;s index (1-indexed). For example, the first node with `val == 1`, the second node with `val == 2`, and so on. The graph is represented in the test case using an adjacency list.


<b>An adjacency list</b> is a collection of unordered <b>lists</b> used to represent a finite graph. Each list describes the set of neighbors of a node in the graph.


The given node will always be the first node with `val = 1`. You must return the **copy of the given node** as a reference to the cloned graph.


 

<strong class="example">Example 1:**

<img alt="" src="https://assets.leetcode.com/uploads/2019/11/04/133_clone_graph_question.png" style="width: 454px; height: 500px;" />

**Input:** adjList = [[2,4],[1,3],[2,4],[1,3]]
**Output:** [[2,4],[1,3],[2,4],[1,3]]
**Explanation:** There are 4 nodes in the graph.
1st node (val = 1)&#39;s neighbors are 2nd node (val = 2) and 4th node (val = 4).
2nd node (val = 2)&#39;s neighbors are 1st node (val = 1) and 3rd node (val = 3).
3rd node (val = 3)&#39;s neighbors are 2nd node (val = 2) and 4th node (val = 4).
4th node (val = 4)&#39;s neighbors are 1st node (val = 1) and 3rd node (val = 3).


<strong class="example">Example 2:**

<img alt="" src="https://assets.leetcode.com/uploads/2020/01/07/graph.png" style="width: 163px; height: 148px;" />

**Input:** adjList = [[]]
**Output:** [[]]
**Explanation:** Note that the input contains one empty list. The graph consists of only one node with val = 1 and it does not have any neighbors.


<strong class="example">Example 3:**



**Input:** adjList = []
**Output:** []
**Explanation:** This an empty graph, it does not have any nodes.


 

**Constraints:**



	- The number of nodes in the graph is in the range `[0, 100]`.
	- `1 <= Node.val <= 100`
	- `Node.val` is unique for each node.
	- There are no repeated edges and no self-loops in the graph.
	- The Graph is connected and all nodes can be visited starting from the given node.

---

## 💻 My Solution

```cpp
/*
// Definition for a Node.
class Node {
public:
    int val;
    vector<Node*> neighbors;
    Node() {
        val = 0;
        neighbors = vector<Node*>();
    }
    Node(int _val) {
        val = _val;
        neighbors = vector<Node*>();
    }
    Node(int _val, vector<Node*> _neighbors) {
        val = _val;
        neighbors = _neighbors;
    }
};
*/

class Solution {
public:
    unordered_map<Node*,Node*> mp;

    Node* cloneGraph(Node* node) {
        if(!node)
            return nullptr;
        if(mp.count(node))
            return mp[node];

        Node* copy=new Node(node->val);
        mp[node]=copy;
        for(Node* nei:node->neighbors)
            copy->neighbors.push_back(cloneGraph(nei));

        return copy;
    }
};

```

---

## 🧪 Sample Test Case

```
[[2,4],[1,3],[2,4],[1,3]]
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
