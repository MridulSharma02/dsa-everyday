<div align="center">

# 👆 925. Long Pressed Name

*Pushed on October 21, 2026 · Problem #136 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 👆 Two Pointers   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 33.2%              |
| **Language**         | 🔠 C++         |

**Tags:** `Two Pointers` `String`

---

## 🧩 Problem Description

Your friend is typing his `name` into a keyboard. Sometimes, when typing a character `c`, the key might get *long pressed*, and the character will be typed 1 or more times.


You examine the `typed` characters of the keyboard. Return `True` if it is possible that it was your friends name, with some characters (possibly none) being long pressed.


 

<strong class="example">Example 1:**



**Input:** name = &quot;alex&quot;, typed = &quot;aaleex&quot;
**Output:** true
**Explanation: **&#39;a&#39; and &#39;e&#39; in &#39;alex&#39; were long pressed.


<strong class="example">Example 2:**



**Input:** name = &quot;saeed&quot;, typed = &quot;ssaaedd&quot;
**Output:** false
**Explanation: **&#39;e&#39; must have been pressed twice, but it was not in the typed output.


 

**Constraints:**



	- `1 <= name.length, typed.length <= 1000`
	- `name` and `typed` consist of only lowercase English letters.

---

## 💻 My Solution

```cpp
// Brute Force
// class Solution {
// public:
//     bool isLongPressedName(string name, string typed) {
//         int i=0;
//         int j=0;
//         while(i<name.size() && j<typed.size()){
//             if(name[i]!=typed[j])
//                 return false;
//             char c=name[i];
//             int count1=0;
//             int count2=0;
//             while(i<name.size() && name[i]==c){
//                 count1++;
//                 i++;
//             }
//             while(j<typed.size() && typed[j]==c){
//                 count2++;
//                 j++;
//             }
//             if(count2<count1)
//                 return false;
//         }

//         return i==name.size() && j==typed.size();
//     }
// };

// Optimized
class Solution {
public:
    bool isLongPressedName(string name, string typed) {
        int i=0;
        int j=0;
        while(j<typed.size()){
            if(i<name.size() && name[i]==typed[j]){
                i++;
                j++;
            }
            else if(j>0 && typed[j]==typed[j-1]){
                j++;
            }
            else{
                return false;
            }
        }

        return i==name.size();
    }
};

```

---

## 🧪 Sample Test Case

```
"alex"
"aaleex"
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Two Pointers** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying two pointers to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
