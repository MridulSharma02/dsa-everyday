<div align="center">

# 💻 1193. Monthly Transactions I

*Solved on June 06, 2026 · Problem #3 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 💻 Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 59.2%              |
| **Language**         | 🔠 PYTHON         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Transactions`


<pre>
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
</pre>

 


Write an SQL query to find for each month and country, the number of transactions and their total amount, the number of approved transactions and their total amount.


Return the result table in **any order**.


The query result format is in the following example.


 

<strong class="example">Example 1:**


<pre>
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
</pre>


---

## 💻 My Solution

```python
# Code not available — session may have expired
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
