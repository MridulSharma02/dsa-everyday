<div align="center">

# 🗄️ 196. Delete Duplicate Emails

*Pushed on June 29, 2026 · Problem #22 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 66.2%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Person`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| email       | varchar |
+-------------+---------+
id is the primary key (column with unique values) for this table.
Each row of this table contains an email. The emails will not contain uppercase letters.


 


Write a solution to** delete** all duplicate emails, keeping only one unique email with the smallest `id`.


For SQL users, please note that you are supposed to write a `DELETE` statement and not a `SELECT` one.


For Pandas users, please note that you are supposed to modify `Person` in place.


After running your script, the answer shown is the `Person` table. The driver will first compile and run your piece of code and then show the `Person` table. The final order of the `Person` table **does not matter**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Person table:
+----+------------------+
| id | email            |
+----+------------------+
| 1  | john@example.com |
| 2  | bob@example.com  |
| 3  | john@example.com |
+----+------------------+
**Output:** 
+----+------------------+
| id | email            |
+----+------------------+
| 1  | john@example.com |
| 2  | bob@example.com  |
+----+------------------+
**Explanation:** john@example.com is repeated two times. We keep the row with the smallest Id = 1.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
DELETE p1
FROM Person p1
JOIN Person p2
ON p1.email=p2.email
AND p1.id>p2.id;

```

---

## 🧪 Sample Test Case

```
{"headers": {"Person": ["id", "email"]}, "rows": {"Person": [[1, "john@example.com"], [2, "bob@example.com"], [3, "john@example.com"]]}}
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
