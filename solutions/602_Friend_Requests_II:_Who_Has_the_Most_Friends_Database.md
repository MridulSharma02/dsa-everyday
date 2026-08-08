<div align="center">

# 🗄️ 602. Friend Requests II: Who Has the Most Friends

*Pushed on August 08, 2026 · Problem #62 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟡 Medium |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 63.3%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `RequestAccepted`



+----------------+---------+
| Column Name    | Type    |
+----------------+---------+
| requester_id   | int     |
| accepter_id    | int     |
| accept_date    | date    |
+----------------+---------+
(requester_id, accepter_id) is the primary key (combination of columns with unique values) for this table.
This table contains the ID of the user who sent the request, the ID of the user who received the request, and the date when the request was accepted.


 


Write a solution to find the people who have the most friends and the most friends number.


The test cases are generated so that only one person has the most friends.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
RequestAccepted table:
+--------------+-------------+-------------+
| requester_id | accepter_id | accept_date |
+--------------+-------------+-------------+
| 1            | 2           | 2016/06/03  |
| 1            | 3           | 2016/06/08  |
| 2            | 3           | 2016/06/08  |
| 3            | 4           | 2016/06/09  |
+--------------+-------------+-------------+
**Output:** 
+----+-----+
| id | num |
+----+-----+
| 3  | 3   |
+----+-----+
**Explanation:** 
The person with id 3 is a friend of people 1, 2, and 4, so he has three friends in total, which is the most number than any others.


 

**Follow up:** In the real world, multiple people could have the same most number of friends. Could you find all these people in this case?

---

## 🪄 Hints
> 💡 Being friends is bidirectional. If you accept someone's adding friend request, both you and the other person will have one more friend.

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT id,COUNT(*) AS num
FROM (
    SELECT requester_id AS id
    FROM RequestAccepted

    UNION ALL

    SELECT accepter_id AS id
    FROM RequestAccepted
) T
GROUP BY id
ORDER BY num DESC
LIMIT 1;

```

---

## 🧪 Sample Test Case

```
{"headers":{"RequestAccepted":["requester_id","accepter_id","accept_date"]},"rows":{"RequestAccepted":[[1,2,"2016/06/03"],[1,3,"2016/06/08"],[2,3,"2016/06/08"],[3,4,"2016/06/09"]]}}
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
