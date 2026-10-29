<div align="center">

# 🗄️ 2356. Number of Unique Subjects Taught by Each Teacher

*Pushed on October 29, 2026 · Problem #144 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 89.4%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Teacher`



+-------------+------+
| Column Name | Type |
+-------------+------+
| teacher_id  | int  |
| subject_id  | int  |
| dept_id     | int  |
+-------------+------+
(subject_id, dept_id) is the primary key (combinations of columns with unique values) of this table.
Each row in this table indicates that the teacher with teacher_id teaches the subject subject_id in the department dept_id.


 


Write a solution to calculate the number of unique subjects each teacher teaches in the university.


Return the result table in **any order**.


The result format is shown in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Teacher table:
+------------+------------+---------+
| teacher_id | subject_id | dept_id |
+------------+------------+---------+
| 1          | 2          | 3       |
| 1          | 2          | 4       |
| 1          | 3          | 3       |
| 2          | 1          | 1       |
| 2          | 2          | 1       |
| 2          | 3          | 1       |
| 2          | 4          | 1       |
+------------+------------+---------+
**Output:**  
+------------+-----+
| teacher_id | cnt |
+------------+-----+
| 1          | 2   |
| 2          | 4   |
+------------+-----+
**Explanation:** 
Teacher 1:
  - They teach subject 2 in departments 3 and 4.
  - They teach subject 3 in department 3.
Teacher 2:
  - They teach subject 1 in department 1.
  - They teach subject 2 in department 1.
  - They teach subject 3 in department 1.
  - They teach subject 4 in department 1.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT teacher_id,COUNT(DISTINCT subject_id) AS cnt 
FROM Teacher
GROUP BY teacher_id;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Teacher":["teacher_id","subject_id","dept_id"]},"rows":{"Teacher":[[1,2,3],[1,2,4],[1,3,3],[2,1,1],[2,2,1],[2,3,1],[2,4,1]]}}
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
