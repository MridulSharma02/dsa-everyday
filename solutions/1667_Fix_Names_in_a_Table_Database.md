<div align="center">

# 🗄️ 1667. Fix Names in a Table

*Pushed on August 07, 2026 · Problem #60 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 60.6%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Users`



+----------------+---------+
| Column Name    | Type    |
+----------------+---------+
| user_id        | int     |
| name           | varchar |
+----------------+---------+
user_id is the primary key (column with unique values) for this table.
This table contains the ID and the name of the user. The name consists of only lowercase and uppercase characters.


 


Write a solution to fix the names so that only the first character is uppercase and the rest are lowercase.


Return the result table ordered by `user_id`.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Users table:
+---------+-------+
| user_id | name  |
+---------+-------+
| 1       | aLice |
| 2       | bOB   |
+---------+-------+
**Output:** 
+---------+-------+
| user_id | name  |
+---------+-------+
| 1       | Alice |
| 2       | Bob   |
+---------+-------+

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT user_id,CONCAT(
                UPPER(LEFT(name, 1)), 
                LOWER(SUBSTRING(name, 2))
) AS name 
FROM Users
ORDER BY user_id;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Users":["user_id","name"]},"rows":{"Users":[[1,"aLice"],[2,"bOB"]]}}
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
