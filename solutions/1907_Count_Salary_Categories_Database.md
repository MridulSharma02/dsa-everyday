<div align="center">

# 🗄️ 1907. Count Salary Categories

*Pushed on June 24, 2026 · Problem #17 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 64.7%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Accounts`



+-------------+------+
| Column Name | Type |
+-------------+------+
| account_id  | int  |
| income      | int  |
+-------------+------+
account_id is the primary key (column with unique values) for this table.
Each row contains information about the monthly income for one bank account.


 


Write a solution to calculate the number of bank accounts for each salary category. The salary categories are:



	- `&quot;Low Salary&quot;`: All the salaries **strictly less** than `$20000`.
	- `&quot;Average Salary&quot;`: All the salaries in the **inclusive** range `[$20000, $50000]`.
	- `&quot;High Salary&quot;`: All the salaries **strictly greater** than `$50000`.


The result table **must** contain all three categories. If there are no accounts in a category, return `0`.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Accounts table:
+------------+--------+
| account_id | income |
+------------+--------+
| 3          | 108939 |
| 2          | 12747  |
| 8          | 87709  |
| 6          | 91796  |
+------------+--------+
**Output:** 
+----------------+----------------+
| category       | accounts_count |
+----------------+----------------+
| Low Salary     | 1              |
| Average Salary | 0              |
| High Salary    | 3              |
+----------------+----------------+
**Explanation:** 
Low Salary: Account 2.
Average Salary: No accounts.
High Salary: Accounts 3, 6, and 8.

---

## 💻 My Solution

```sql
SELECT C.category, IFNULL(T.accounts_count, 0) AS accounts_count
FROM (
    SELECT 'Low Salary' AS category
    UNION ALL
    SELECT 'Average Salary'
    UNION ALL
    SELECT 'High Salary' ) AS C
LEFT JOIN (
    SELECT category, COUNT(*) AS accounts_count
    FROM (
        SELECT CASE
            WHEN income < 20000 THEN 'Low Salary'
            WHEN income > 50000 THEN 'High Salary'
            ELSE 'Average Salary'
        END AS category
        FROM Accounts) AS A
    GROUP BY category) AS T
ON C.category = T.category;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Accounts":["account_id","income"]},"rows":{"Accounts":[[3,108939],[2,12747],[8,87709],[6,91796]]}}
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
