<div align="center">

# 🗄️ 1070. Product Sales Analysis III

*Pushed on November 13, 2026 · Problem #159 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 47.0%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Sales`



+-------------+-------+
| Column Name | Type  |
+-------------+-------+
| sale_id     | int   |
| product_id  | int   |
| year        | int   |
| quantity    | int   |
| price       | int   |
+-------------+-------+
(sale_id, year) is the primary key (combination of columns with unique values) of this table.
Each row records a sale of a product in a given year.
A product may have multiple sales entries in the same year.
Note that the per-unit price.



Write a solution to find all sales that occurred in the <strong data-end="967" data-start="953">first year** each product was sold.


<ul data-end="1234" data-start="992">
	<li data-end="1078" data-start="992">
	<p data-end="1078" data-start="994">For each <code data-end="1015" data-start="1003">product_id`, identify the earliest <code data-end="1045" data-start="1039">year` it appears in the <code data-end="1071" data-start="1064">Sales` table.

	
	<li data-end="1140" data-start="1079">
	<p data-end="1140" data-start="1081">Return <strong data-end="1095" data-start="1088">all** sales entries for that product in that year.

	


<p data-end="1234" data-start="1143">Return a table with the following columns: **product_id**,** first_year**, **quantity, **and** price**.<br />
Return the result in any order.


 

<strong class="example">Example 1:**



**Input:** 
Sales table:
+---------+------------+------+----------+-------+
| sale_id | product_id | year | quantity | price |
+---------+------------+------+----------+-------+ 
| 1       | 100        | 2008 | 10       | 5000  |
| 2       | 100        | 2009 | 12       | 5000  |
| 7       | 200        | 2011 | 15       | 9000  |
+---------+------------+------+----------+-------+

**Output:** 
+------------+------------+----------+-------+
| product_id | first_year | quantity | price |
+------------+------------+----------+-------+ 
| 100        | 2008       | 10       | 5000  |
| 200        | 2011       | 15       | 9000  |
+------------+------------+----------+-------+

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT S.product_id,F.first_year,S.quantity,S.price
FROM Sales AS S
JOIN (SELECT product_id,MIN(year) AS first_year FROM Sales GROUP BY product_id) AS F
ON S.product_id=F.product_id
AND S.year=F.first_year;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Sales":["sale_id","product_id","year","quantity","price"]},"rows":{"Sales":[[1,100,2008,10,5000],[2,100,2009,12,5000],[7,200,2011,15,9000]]}}
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
