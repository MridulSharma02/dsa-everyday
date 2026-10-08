<div align="center">

# 🗄️ 1341. Movie Rating

*Pushed on October 08, 2026 · Problem #123 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 44.7%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Movies`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| movie_id      | int     |
| title         | varchar |
+---------------+---------+
movie_id is the primary key (column with unique values) for this table.
title is the name of the movie.
Each movie has a unique title.

Table: `Users`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| user_id       | int     |
| name          | varchar |
+---------------+---------+
user_id is the primary key (column with unique values) for this table.
The column &#39;name&#39; has unique values.


Table: `MovieRating`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| movie_id      | int     |
| user_id       | int     |
| rating        | int     |
| created_at    | date    |
+---------------+---------+
(movie_id, user_id) is the primary key (column with unique values) for this table.
This table contains the rating of a movie by a user in their review.
created_at is the user&#39;s review date. 


 


Write a solution to:



	- Find the name of the user who has rated the greatest number of movies. In case of a tie, return the lexicographically smaller user name.
	- Find the movie name with the **highest average** rating in `February 2020`. In case of a tie, return the lexicographically smaller movie name.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Movies table:
+-------------+--------------+
| movie_id    |  title       |
+-------------+--------------+
| 1           | Avengers     |
| 2           | Frozen 2     |
| 3           | Joker        |
+-------------+--------------+
Users table:
+-------------+--------------+
| user_id     |  name        |
+-------------+--------------+
| 1           | Daniel       |
| 2           | Monica       |
| 3           | Maria        |
| 4           | James        |
+-------------+--------------+
MovieRating table:
+-------------+--------------+--------------+-------------+
| movie_id    | user_id      | rating       | created_at  |
+-------------+--------------+--------------+-------------+
| 1           | 1            | 3            | 2020-01-12  |
| 1           | 2            | 4            | 2020-02-11  |
| 1           | 3            | 2            | 2020-02-12  |
| 1           | 4            | 1            | 2020-01-01  |
| 2           | 1            | 5            | 2020-02-17  | 
| 2           | 2            | 2            | 2020-02-01  | 
| 2           | 3            | 2            | 2020-03-01  |
| 3           | 1            | 3            | 2020-02-22  | 
| 3           | 2            | 4            | 2020-02-25  | 
+-------------+--------------+--------------+-------------+
**Output:** 
+--------------+
| results      |
+--------------+
| Daniel       |
| Frozen 2     |
+--------------+
**Explanation:** 
Daniel and Monica have rated 3 movies (&quot;Avengers&quot;, &quot;Frozen 2&quot; and &quot;Joker&quot;) but Daniel is smaller lexicographically.
Frozen 2 and Joker have a rating average of 3.5 in February but Frozen 2 is smaller lexicographically.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
(SELECT U.name AS results
FROM MovieRating AS M
JOIN Users AS U
ON M.user_id=U.user_id
GROUP BY M.user_id
ORDER BY COUNT(*) DESC, name ASC
LIMIT 1)

UNION ALL

(SELECT A.title AS results
FROM MovieRating AS M
JOIN Movies AS A
ON M.movie_id=A.movie_id
WHERE created_at BETWEEN '2020-02-01' AND '2020-02-29'
GROUP BY A.movie_id
ORDER BY AVG(rating) DESC, title ASC
LIMIT 1);

```

---

## 🧪 Sample Test Case

```
{"headers": {"Movies": ["movie_id", "title"], "Users": ["user_id", "name"], "MovieRating": ["movie_id", "user_id", "rating", "created_at"]}, "rows": {"Movies": [[1, "Avengers"], [2, "Frozen 2"], [3, "Joker"]], "Users": [[1, "Daniel"], [2, "Monica"], [3, "Maria"], [4, "James"]], "MovieRating": [[1, 1, 3, "2020-01-12"], [1, 2, 4, "2020-02-11"], [1, 3, 2, "2020-02-12"], [1, 4, 1, "2020-01-01"], [2, 1, 5, "2020-02-17"], [2, 2, 2, "2020-02-01"], [2, 3, 2, "2020-03-01"], [3, 1, 3, "2020-02-22"], [3, 2, 4, "2020-02-25"]]}}
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
