<div align="center">

# 🗄️ 1148. Article Views I

*Pushed on June 10, 2026 · Problem #3 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 76.6%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Views`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| article_id    | int     |
| author_id     | int     |
| viewer_id     | int     |
| view_date     | date    |
+---------------+---------+
There is no primary key (column with unique values) for this table, the table may have duplicate rows.
Each row of this table indicates that some viewer viewed an article (written by some author) on some date. 
Note that equal author_id and viewer_id indicate the same person.


 


Write a solution to find all the authors that viewed at least one of their own articles.


Return the result table sorted by `id` in ascending order.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Views table:
+------------+-----------+-----------+------------+
| article_id | author_id | viewer_id | view_date  |
+------------+-----------+-----------+------------+
| 1          | 3         | 5         | 2019-08-01 |
| 1          | 3         | 6         | 2019-08-02 |
| 2          | 7         | 7         | 2019-08-01 |
| 2          | 7         | 6         | 2019-08-02 |
| 4          | 7         | 1         | 2019-07-22 |
| 3          | 4         | 4         | 2019-07-21 |
| 3          | 4         | 4         | 2019-07-21 |
+------------+-----------+-----------+------------+
**Output:** 
+------+
| id   |
+------+
| 4    |
| 7    |
+------+

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT DISTINCT author_id AS id FROM Views WHERE author_id=viewer_id ORDER BY id;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Views":["article_id","author_id","viewer_id","view_date"]},"rows":{"Views":[[1,3,5,"2019-08-01"],[1,3,6,"2019-08-02"],[2,7,7,"2019-08-01"],[2,7,6,"2019-08-02"],[4,7,1,"2019-07-22"],[3,4,4,"2019-07-21"],[3,4,4,"2019-07-21"]]}}
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
