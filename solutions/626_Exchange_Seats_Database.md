<div align="center">

# 🗄️ 626. Exchange Seats

*Pushed on July 14, 2026 · Problem #37 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 74.4%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Seat`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| student     | varchar |
+-------------+---------+
id is the primary key (unique value) column for this table.
Each row of this table indicates the name and the ID of a student.
The ID sequence always starts from 1 and increments continuously.


 


Write a solution to swap the seat id of every two consecutive students. If the number of students is odd, the id of the last student is not swapped.


Return the result table ordered by `id` **in ascending order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Seat table:
+----+---------+
| id | student |
+----+---------+
| 1  | Abbot   |
| 2  | Doris   |
| 3  | Emerson |
| 4  | Green   |
| 5  | Jeames  |
+----+---------+
**Output:** 
+----+---------+
| id | student |
+----+---------+
| 1  | Doris   |
| 2  | Abbot   |
| 3  | Green   |
| 4  | Emerson |
| 5  | Jeames  |
+----+---------+
**Explanation:** 
Note that if the number of students is odd, there is no need to change the last one&#39;s seat.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT CASE
            WHEN id=(SELECT MAX(id) FROM Seat) AND id%2=1 THEN id
            WHEN id%2=1 THEN id+1 ELSE id-1 
       END AS id,student
FROM Seat
ORDER BY id;

```

---

## 🧪 Sample Test Case

```
{"headers": {"Seat": ["id","student"]}, "rows": {"Seat": [[1,"Abbot"],[2,"Doris"],[3,"Emerson"],[4,"Green"],[5,"Jeames"]]}}
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
