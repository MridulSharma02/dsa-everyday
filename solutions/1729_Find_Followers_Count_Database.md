<div align="center">

# 🗄️ 1729. Find Followers Count

*Pushed on July 17, 2026 · Problem #40 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 69.6%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Followers`



+-------------+------+
| Column Name | Type |
+-------------+------+
| user_id     | int  |
| follower_id | int  |
+-------------+------+
(user_id, follower_id) is the primary key (combination of columns with unique values) for this table.
This table contains the IDs of a user and a follower in a social media app where the follower follows the user.

 


Write a solution that will, for each user, return the number of followers.


Return the result table ordered by `user_id` in ascending order.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Followers table:
+---------+-------------+
| user_id | follower_id |
+---------+-------------+
| 0       | 1           |
| 1       | 0           |
| 2       | 0           |
| 2       | 1           |
+---------+-------------+
**Output:** 
+---------+----------------+
| user_id | followers_count|
+---------+----------------+
| 0       | 1              |
| 1       | 1              |
| 2       | 2              |
+---------+----------------+
**Explanation:** 
The followers of 0 are {1}
The followers of 1 are {0}
The followers of 2 are {0,1}

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT user_id,COUNT(follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Followers":["user_id","follower_id"]},"rows":{"Followers":[["0","1"],["1","0"],["2","0"],["2","1"]]}}
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
