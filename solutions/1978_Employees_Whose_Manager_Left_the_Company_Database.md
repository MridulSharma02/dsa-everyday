<div align="center">

# 🗄️ 1978. Employees Whose Manager Left the Company

*Pushed on July 06, 2026 · Problem #29 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 48.8%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Employees`



+-------------+----------+
| Column Name | Type     |
+-------------+----------+
| employee_id | int      |
| name        | varchar  |
| manager_id  | int      |
| salary      | int      |
+-------------+----------+
In SQL, employee_id is the primary key for this table.
This table contains information about the employees, their salary, and the ID of their manager. Some employees do not have a manager (manager_id is null). 


 


Find the IDs of the employees whose salary is strictly less than `$30000` and whose manager left the company. When a manager leaves the company, their information is deleted from the `Employees` table, but the reports still have their `manager_id` set to the manager that left.


Return the result table ordered by `employee_id`.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input: ** 
Employees table:
+-------------+-----------+------------+--------+
| employee_id | name      | manager_id | salary |
+-------------+-----------+------------+--------+
| 3           | Mila      | 9          | 60301  |
| 12          | Antonella | null       | 31000  |
| 13          | Emery     | null       | 67084  |
| 1           | Kalel     | 11         | 21241  |
| 9           | Mikaela   | null       | 50937  |
| 11          | Joziah    | 6          | 28485  |
+-------------+-----------+------------+--------+
**Output:** 
+-------------+
| employee_id |
+-------------+
| 11          |
+-------------+

**Explanation:** 
The employees with a salary less than $30000 are 1 (Kalel) and 11 (Joziah).
Kalel&#39;s manager is employee 11, who is still in the company (Joziah).
Joziah&#39;s manager is employee 6, who left the company because there is no row for employee 6 as it was deleted.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT employee_id
FROM Employees
WHERE manager_id IS NOT NULL
AND manager_id NOT IN (SELECT employee_id FROM Employees)
AND salary<30000
ORDER BY employee_id;

```

---

## 🧪 Sample Test Case

```
{"headers": {"Employees": ["employee_id", "name", "manager_id", "salary"]}, "rows": {"Employees": [[3, "Mila", 9, 60301], [12, "Antonella", null, 31000], [13, "Emery", null, 67084], [1, "Kalel", 11, 21241], [9, "Mikaela", null, 50937], [11, "Joziah", 6, 28485]]}}
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
