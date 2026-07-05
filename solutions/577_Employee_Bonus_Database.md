<div align="center">

# 🗄️ 577. Employee Bonus

*Pushed on July 05, 2026 · Problem #28 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 77.6%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Employee`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| empId       | int     |
| name        | varchar |
| supervisor  | int     |
| salary      | int     |
+-------------+---------+
empId is the column with unique values for this table.
Each row of this table indicates the name and the ID of an employee in addition to their salary and the id of their manager.


 


Table: `Bonus`



+-------------+------+
| Column Name | Type |
+-------------+------+
| empId       | int  |
| bonus       | int  |
+-------------+------+
empId is the column of unique values for this table.
empId is a foreign key (reference column) to empId from the Employee table.
Each row of this table contains the id of an employee and their respective bonus.


 


Write a solution to report the name and bonus amount of each employee who satisfies either of the following:



	- The employee has a bonus **less than** `1000`.
	- The employee did not get any bonus.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Employee table:
+-------+--------+------------+--------+
| empId | name   | supervisor | salary |
+-------+--------+------------+--------+
| 3     | Brad   | null       | 4000   |
| 1     | John   | 3          | 1000   |
| 2     | Dan    | 3          | 2000   |
| 4     | Thomas | 3          | 4000   |
+-------+--------+------------+--------+
Bonus table:
+-------+-------+
| empId | bonus |
+-------+-------+
| 2     | 500   |
| 4     | 2000  |
+-------+-------+
**Output:** 
+------+-------+
| name | bonus |
+------+-------+
| Brad | null  |
| John | null  |
| Dan  | 500   |
+------+-------+

---

## 🪄 Hints
> 💡 If the EmpId in table Employee has no match in table Bonus, we consider that the corresponding bonus is null and null is smaller than 1000.
> 💡 Inner join is the default join, we can solve the mismatching problem by using outer join.

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT name,bonus
FROM Employee AS E
LEFT JOIN Bonus AS B
ON E.empId=B.empId
WHERE Bonus<1000 or Bonus IS NULL;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Employee":["empId","name","supervisor","salary"],"Bonus":["empId","bonus"]},"rows":{"Employee":[[3,"Brad",null,4000],[1,"John",3,1000],[2,"Dan",3,2000],[4,"Thomas",3,4000]],"Bonus":[[2,500],[4,2000]]}}
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
