<div align="center">

# 🗄️ 1164. Product Price at a Given Date

*Pushed on November 12, 2026 · Problem #157 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 59.1%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Products`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| product_id    | int     |
| new_price     | int     |
| change_date   | date    |
+---------------+---------+
(product_id, change_date) is the primary key (combination of columns with unique values) of this table.
Each row of this table indicates that the price of some product was changed to a new price at some date.

Initially, all products have price 10.


Write a solution to find the prices of all products on the date `2019-08-16`.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Products table:
+------------+-----------+-------------+
| product_id | new_price | change_date |
+------------+-----------+-------------+
| 1          | 20        | 2019-08-14  |
| 2          | 50        | 2019-08-14  |
| 1          | 30        | 2019-08-15  |
| 1          | 35        | 2019-08-16  |
| 2          | 65        | 2019-08-17  |
| 3          | 20        | 2019-08-18  |
+------------+-----------+-------------+
**Output:** 
+------------+-------+
| product_id | price |
+------------+-------+
| 2          | 50    |
| 1          | 35    |
| 3          | 10    |
+------------+-------+

---

## 💻 My Solution

```sql
SELECT P.product_id, P.new_price AS price
FROM Products P
JOIN (
    SELECT product_id, MAX(change_date) AS latest_date
    FROM Products
    WHERE change_date<='2019-08-16'
    GROUP BY product_id
) T
ON P.product_id=T.product_id
AND P.change_date=T.latest_date

UNION

SELECT product_id, 10 AS price
FROM Products
GROUP BY product_id
HAVING MIN(change_date)>'2019-08-16';

```

---

## 🧪 Sample Test Case

```
{"headers":{"Products":["product_id","new_price","change_date"]},"rows":{"Products":[[1,20,"2019-08-14"],[2,50,"2019-08-14"],[1,30,"2019-08-15"],[1,35,"2019-08-16"],[2,65,"2019-08-17"],[3,20,"2019-08-18"]]}}
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
