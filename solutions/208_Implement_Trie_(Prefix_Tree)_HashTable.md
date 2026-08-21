<div align="center">

# 🗂️ 208. Implement Trie (Prefix Tree)

*Pushed on August 21, 2026 · Problem #75 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗂️ Hash Table   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(n)`            |
| **Acceptance Rate**  | ✅ 69.9%              |
| **Language**         | 🔠 C++         |

**Tags:** `Hash Table` `String` `Design` `Trie`

---

## 🧩 Problem Description

A <a href="https://en.wikipedia.org/wiki/Trie" target="_blank">**trie**</a> (pronounced as &quot;try&quot;) or **prefix tree** is a tree data structure used to efficiently store and retrieve keys in a dataset of strings. There are various applications of this data structure, such as autocomplete and spellchecker.


Implement the Trie class:



	- `Trie()` Initializes the trie object.
	- `void insert(String word)` Inserts the string `word` into the trie.
	- `boolean search(String word)` Returns `true` if the string `word` is in the trie (i.e., was inserted before), and `false` otherwise.
	- `boolean startsWith(String prefix)` Returns `true` if there is a previously inserted string `word` that has the prefix `prefix`, and `false` otherwise.


 

<strong class="example">Example 1:**



**Input**
[&quot;Trie&quot;, &quot;insert&quot;, &quot;search&quot;, &quot;search&quot;, &quot;startsWith&quot;, &quot;insert&quot;, &quot;search&quot;]
[[], [&quot;apple&quot;], [&quot;apple&quot;], [&quot;app&quot;], [&quot;app&quot;], [&quot;app&quot;], [&quot;app&quot;]]
**Output**
[null, null, true, false, true, null, true]

**Explanation**
Trie trie = new Trie();
trie.insert(&quot;apple&quot;);
trie.search(&quot;apple&quot;);   // return True
trie.search(&quot;app&quot;);     // return False
trie.startsWith(&quot;app&quot;); // return True
trie.insert(&quot;app&quot;);
trie.search(&quot;app&quot;);     // return True


 

**Constraints:**



	- `1 <= word.length, prefix.length <= 2000`
	- `word` and `prefix` consist only of lowercase English letters.
	- At most `3 * 10^4` calls **in total** will be made to `insert`, `search`, and `startsWith`.

---

## 💻 My Solution

```cpp
class Trie {
public:
    struct Node {
        Node* child[26];
        bool end;
        Node() {
            end = false;
            for (int i = 0; i < 26; i++) child[i] = nullptr;
        }
    };

    Node* root;

    Trie() {
        root = new Node();
    }

    void insert(string word) {
        Node* curr = root;
        for (char c : word) {
            int idx = c - 'a';
            if (!curr->child[idx]) curr->child[idx] = new Node();
            curr = curr->child[idx];
        }
        curr->end = true;
    }

    bool search(string word) {
        Node* curr = root;
        for (char c : word) {
            int idx = c - 'a';
            if (!curr->child[idx]) return false;
            curr = curr->child[idx];
        }
        return curr->end;
    }

    bool startsWith(string prefix) {
        Node* curr = root;
        for (char c : prefix) {
            int idx = c - 'a';
            if (!curr->child[idx]) return false;
            curr = curr->child[idx];
        }
        return true;
    }
};

```

---

## 🧪 Sample Test Case

```
["Trie","insert","search","search","startsWith","insert","search"]
[[],["apple"],["apple"],["app"],["app"],["app"],["app"]]
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
