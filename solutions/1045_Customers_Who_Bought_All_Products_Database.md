<div align="center">

# 🗄️ 1045. Customers Who Bought All Products

*Pushed on June 27, 2026 · Problem #20 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.1%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Customer`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| customer_id | int     |
| product_key | int     |
+-------------+---------+
This table may contain duplicates rows. 
`customer_id` is not NULL`.`
product_key is a foreign key (reference column) to `Product` table.


 


Table: `Product`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| product_key | int     |
+-------------+---------+
product_key is the primary key (column with unique values) for this table.


 


Write a solution to report the customer ids from the `Customer` table that bought all the products in the `Product` table.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Customer table:
+-------------+-------------+
| customer_id | product_key |
+-------------+-------------+
| 1           | 5           |
| 2           | 6           |
| 3           | 5           |
| 3           | 6           |
| 1           | 6           |
+-------------+-------------+
Product table:
+-------------+
| product_key |
+-------------+
| 5           |
| 6           |
+-------------+
**Output:** 
+-------------+
| customer_id |
+-------------+
| 1           |
| 3           |
+-------------+
**Explanation:** 
The customers who bought all the products (5 and 6) are customers with IDs 1 and 3.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT customer_id
FROM Customer
GROUP BY customer_id
HAVING COUNT(DISTINCT product_key)=(SELECT COUNT(*) FROM Product);

```

---

## 🧪 Sample Test Case

```
{"headers":{"Customer":["customer_id","product_key"],"Product":["product_key"]},"rows":{"Customer":[[1,5],[2,6],[3,5],[3,6],[1,6]],"Product":[[5],[6]]}}
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
