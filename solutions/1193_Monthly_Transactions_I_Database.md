<div align="center">

# 🗄️ 1193. Monthly Transactions I

*Pushed on October 06, 2026 · Problem #121 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 60.1%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Transactions`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| id            | int     |
| country       | varchar |
| state         | enum    |
| amount        | int     |
| trans_date    | date    |
+---------------+---------+
id is the primary key of this table.
The table has information about incoming transactions.
The state column is an enum of type [&quot;approved&quot;, &quot;declined&quot;].


 


Write an SQL query to find for each month and country, the number of transactions and their total amount, the number of approved transactions and their total amount.


Return the result table in **any order**.


The query result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Transactions table:
+------+---------+----------+--------+------------+
| id   | country | state    | amount | trans_date |
+------+---------+----------+--------+------------+
| 121  | US      | approved | 1000   | 2018-12-18 |
| 122  | US      | declined | 2000   | 2018-12-19 |
| 123  | US      | approved | 2000   | 2019-01-01 |
| 124  | DE      | approved | 2000   | 2019-01-07 |
+------+---------+----------+--------+------------+
**Output:** 
+----------+---------+-------------+----------------+--------------------+-----------------------+
| month    | country | trans_count | approved_count | trans_total_amount | approved_total_amount |
+----------+---------+-------------+----------------+--------------------+-----------------------+
| 2018-12  | US      | 2           | 1              | 3000               | 1000                  |
| 2019-01  | US      | 1           | 1              | 2000               | 2000                  |
| 2019-01  | DE      | 1           | 1              | 2000               | 2000                  |
+----------+---------+-------------+----------------+--------------------+-----------------------+

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT DATE_FORMAT(trans_date,"%Y-%m") AS month,
       country,
       COUNT(*) AS trans_count,
       SUM(CASE WHEN state="approved" THEN 1 ELSE 0 END) AS approved_count,
       SUM(amount) AS trans_total_amount,
       SUM(CASE WHEN state="approved" THEN amount ELSE 0 END) AS approved_total_amount
FROM Transactions
GROUP BY month,country;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Transactions":["id","country","state","amount","trans_date"]},"rows":{"Transactions":[[121,"US","approved",1000,"2018-12-18"],[122,"US","declined",2000,"2018-12-19"],[123,"US","approved",2000,"2019-01-01"],[124,"DE","approved",2000,"2019-01-07"]]}}
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
