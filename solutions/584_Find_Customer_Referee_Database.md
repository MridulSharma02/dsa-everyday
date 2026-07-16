<div align="center">

# 🗄️ 584. Find Customer Referee

*Pushed on July 16, 2026 · Problem #39 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 73.1%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Customer`



+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| id          | int     |
| name        | varchar |
| referee_id  | int     |
+-------------+---------+
In SQL, id is the primary key column for this table.
Each row of this table indicates the id of a customer, their name, and the id of the customer who referred them.


 


Find the names of the customer that are either:



	- **referred by** any customer with `id != 2`.
	- **not referred by** any customer.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Customer table:
+----+------+------------+
| id | name | referee_id |
+----+------+------------+
| 1  | Will | null       |
| 2  | Jane | null       |
| 3  | Alex | 2          |
| 4  | Bill | null       |
| 5  | Zack | 1          |
| 6  | Mark | 2          |
+----+------+------------+
**Output:** 
+------+
| name |
+------+
| Will |
| Jane |
| Bill |
| Zack |
+------+

---

## 🪄 Hints
> 💡 Be careful of the NULL value

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT name FROM Customer WHERE referee_id!=2 OR referee_id IS NULL;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Customer":["id","name","referee_id"]},"rows":{"Customer":[[1,"Will",null],[2,"Jane",null],[3,"Alex",2],[4,"Bill",null],[5,"Zack",1],[6,"Mark",2]]}}
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
