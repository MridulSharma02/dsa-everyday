<div align="center">

# 💻 1211. Queries Quality and Percentage

*Solved on June 06, 2026 · Problem #2 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 💻 Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 53.3%              |
| **Language**         | 🔠 PYTHON         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Queries`


<pre>
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| query_name  | varchar |
| result      | varchar |
| position    | int     |
| rating      | int     |
+-------------+---------+
This table may have duplicate rows.
This table contains information collected from some queries on a database.
The `position` column has a value from **1** to **500**.
The `rating` column has a value from **1** to **5**. Query with `rating` less than 3 is a poor query.
</pre>

 


We define query `quality` as:


<blockquote>
The average of the ratio between query rating and its position.

</blockquote>

We also define `poor query percentage` as:


<blockquote>
The percentage of all queries with rating less than 3.

</blockquote>

Write a solution to find each `query_name`, the `quality` and `poor_query_percentage`.


Both `quality` and `poor_query_percentage` should be **rounded to 2 decimal places**.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**


<pre>
**Input:** 
Queries table:
+------------+-------------------+----------+--------+
| query_name | result            | position | rating |
+------------+-------------------+----------+--------+
| Dog        | Golden Retriever  | 1        | 5      |
| Dog        | German Shepherd   | 2        | 5      |
| Dog        | Mule              | 200      | 1      |
| Cat        | Shirazi           | 5        | 2      |
| Cat        | Siamese           | 3        | 3      |
| Cat        | Sphynx            | 7        | 4      |
+------------+-------------------+----------+--------+
**Output:** 
+------------+---------+-----------------------+
| query_name | quality | poor_query_percentage |
+------------+---------+-----------------------+
| Dog        | 2.50    | 33.33                 |
| Cat        | 0.66    | 33.33                 |
+------------+---------+-----------------------+
**Explanation:** 
Dog queries quality is ((5 / 1) + (5 / 2) + (1 / 200)) / 3 = 2.50
Dog queries poor_ query_percentage is (1 / 3) * 100 = 33.33

Cat queries quality equals ((2 / 5) + (3 / 3) + (4 / 7)) / 3 = 0.66
Cat queries poor_ query_percentage is (1 / 3) * 100 = 33.33
</pre>


---

## 💻 My Solution

```python
# Code not available — session may have expired
```

---

## 🧪 Sample Test Case

```
{"headers":{"Queries":["query_name","result","position","rating"]},"rows":{"Queries":[["Dog","Golden Retriever",1,5],["Dog","German Shepherd",2,5],["Dog","Mule",200,1],["Cat","Shirazi",5,2],["Cat","Siamese",3,3],["Cat","Sphynx",7,4]]}}
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
