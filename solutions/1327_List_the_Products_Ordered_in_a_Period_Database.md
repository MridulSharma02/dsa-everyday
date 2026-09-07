<div align="center">

# 🗄️ 1327. List the Products Ordered in a Period

*Pushed on September 07, 2026 · Problem #92 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 72.1%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Products`



+------------------+---------+
| Column Name      | Type    |
+------------------+---------+
| product_id       | int     |
| product_name     | varchar |
| product_category | varchar |
+------------------+---------+
product_id is the primary key (column with unique values) for this table.
This table contains data about the company&#39;s products.


 


Table: `Orders`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| product_id    | int     |
| order_date    | date    |
| unit          | int     |
+---------------+---------+
This table may have duplicate rows.
product_id is a foreign key (reference column) to the Products table.
unit is the number of products ordered in order_date.


 


Write a solution to get the names of products that have at least `100` units ordered in **February 2020** and their amount.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Products table:
+-------------+-----------------------+------------------+
| product_id  | product_name          | product_category |
+-------------+-----------------------+------------------+
| 1           | Leetcode Solutions    | Book             |
| 2           | Jewels of Stringology | Book             |
| 3           | HP                    | Laptop           |
| 4           | Lenovo                | Laptop           |
| 5           | Leetcode Kit          | T-shirt          |
+-------------+-----------------------+------------------+
Orders table:
+--------------+--------------+----------+
| product_id   | order_date   | unit     |
+--------------+--------------+----------+
| 1            | 2020-02-05   | 60       |
| 1            | 2020-02-10   | 70       |
| 2            | 2020-01-18   | 30       |
| 2            | 2020-02-11   | 80       |
| 3            | 2020-02-17   | 2        |
| 3            | 2020-02-24   | 3        |
| 4            | 2020-03-01   | 20       |
| 4            | 2020-03-04   | 30       |
| 4            | 2020-03-04   | 60       |
| 5            | 2020-02-25   | 50       |
| 5            | 2020-02-27   | 50       |
| 5            | 2020-03-01   | 50       |
+--------------+--------------+----------+
**Output:** 
+--------------------+---------+
| product_name       | unit    |
+--------------------+---------+
| Leetcode Solutions | 130     |
| Leetcode Kit       | 100     |
+--------------------+---------+
**Explanation:** 
Products with product_id = 1 is ordered in February a total of (60 + 70) = 130.
Products with product_id = 2 is ordered in February a total of 80.
Products with product_id = 3 is ordered in February a total of (2 + 3) = 5.
Products with product_id = 4 was not ordered in February 2020.
Products with product_id = 5 is ordered in February a total of (50 + 50) = 100.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT P.product_name,SUM(O.unit) AS unit
FROM Products AS P
JOIN Orders AS O
ON P.product_id=O.product_id
WHERE O.order_date>='2020-02-01'
AND O.order_date<'2020-03-01'
GROUP BY P.product_id, P.product_name
HAVING SUM(O.unit) >= 100;

```

---

## 🧪 Sample Test Case

```
{"headers": {"Products": ["product_id", "product_name", "product_category"], "Orders": ["product_id", "order_date", "unit"]}, "rows": {"Products": [[1, "Leetcode Solutions", "Book"], [2, "Jewels of Stringology", "Book"], [3, "HP", "Laptop"], [4, "Lenovo", "Laptop"], [5, "Leetcode Kit", "T-shirt"]], "Orders": [[1, "2020-02-05", 60], [1, "2020-02-10", 70], [2, "2020-01-18", 30], [2, "2020-02-11", 80], [3, "2020-02-17", 2], [3, "2020-02-24", 3], [4, "2020-03-01", 20], [4, "2020-03-04", 30], [4, "2020-03-04", 60], [5, "2020-02-25", 50], [5, "2020-02-27", 50], [5, "2020-03-01", 50]]}}
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
