<div align="center">

# 🗄️ 619. Biggest Single Number

*Pushed on June 16, 2026 · Problem #9 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 71.4%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `MyNumbers`



+-------------+------+
| Column Name | Type |
+-------------+------+
| num         | int  |
+-------------+------+
This table may contain duplicates (In other words, there is no primary key for this table in SQL).
Each row of this table contains an integer.


 


A **single number** is a number that appeared only once in the `MyNumbers` table.


Find the largest **single number**. If there is no **single number**, report `null`.


The result format is in the following example.

<ptable> </ptable>
 

<strong class="example">Example 1:**



**Input:** 
MyNumbers table:
+-----+
| num |
+-----+
| 8   |
| 8   |
| 3   |
| 3   |
| 1   |
| 4   |
| 5   |
| 6   |
+-----+
**Output:** 
+-----+
| num |
+-----+
| 6   |
+-----+
**Explanation:** The single numbers are 1, 4, 5, and 6.
Since 6 is the largest single number, we return it.


<strong class="example">Example 2:**



**Input:** 
MyNumbers table:
+-----+
| num |
+-----+
| 8   |
| 8   |
| 7   |
| 7   |
| 3   |
| 3   |
| 3   |
+-----+
**Output:** 
+------+
| num  |
+------+
| null |
+------+
**Explanation:** There are no single numbers in the input table so we return null.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT MAX(num) AS num
FROM (
    SELECT num
    FROM MyNumbers
    GROUP BY num
    HAVING COUNT(*) = 1
) AS S;

```

---

## 🧪 Sample Test Case

```
{"headers": {"MyNumbers": ["num"]}, "rows": {"MyNumbers": [[8],[8],[3],[3],[1],[4],[5],[6]]}}
```

---

## 🔍 Approach & Intuition

> This problem primarily involves **Database** techniques.
> The key insight is to leverage `O(n)` time complexity
> by applying database to efficiently reach the solution.
> Space usage is kept at `O(1)` by optimizing auxiliary structures.

---

<div align="center">

*Part of my [dsa-everyday](https://github.com/MridulSharma02/dsa-everyday) journey*
*🔥 Consistency is the key to mastery*

</div>
