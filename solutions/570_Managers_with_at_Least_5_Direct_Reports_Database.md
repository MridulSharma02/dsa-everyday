<div align="center">

# 🗄️ 570. Managers with at Least 5 Direct Reports

*Pushed on September 16, 2026 · Problem #101 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 49.6%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Employee`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| name        | varchar |
| department  | varchar |
| managerId   | int     |
+-------------+---------+
id is the primary key (column with unique values) for this table.
Each row of this table indicates the name of an employee, their department, and the id of their manager.
If managerId is null, then the employee does not have a manager.
No employee will be the manager of themself.


 


Write a solution to find managers with at least **five direct reports**.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Employee table:
+-----+-------+------------+-----------+
| id  | name  | department | managerId |
+-----+-------+------------+-----------+
| 101 | John  | A          | null      |
| 102 | Dan   | A          | 101       |
| 103 | James | A          | 101       |
| 104 | Amy   | A          | 101       |
| 105 | Anne  | A          | 101       |
| 106 | Ron   | B          | 101       |
+-----+-------+------------+-----------+
**Output:** 
+------+
| name |
+------+
| John |
+------+

---

## 🪄 Hints
> 💡 Try to get all the mangerIDs that have count bigger than 5
> 💡 Use the last hint's result as a table and do join with origin table at id equals to managerId

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT E1.name
FROM Employee AS E1
JOIN Employee AS E2
ON E2.managerId=E1.id
GROUP BY E1.id
HAVING COUNT(*)>=5;

```

---

## 🧪 Sample Test Case

```
{"headers": {"Employee": ["id", "name", "department", "managerId"]}, "rows": {"Employee": [[101, "John", "A", null],[102, "Dan", "A", 101], [103, "James", "A", 101], [104, "Amy", "A", 101], [105, "Anne", "A", 101], [106, "Ron", "B", 101]]}}
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
