<div align="center">

# 🗄️ 1661. Average Time of Process per Machine

*Pushed on June 13, 2026 · Problem #6 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 66.8%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Activity`



+----------------+---------+
| Column Name    | Type    |
+----------------+---------+
| machine_id     | int     |
| process_id     | int     |
| activity_type  | enum    |
| timestamp      | float   |
+----------------+---------+
The table shows the user activities for a factory website.
(machine_id, process_id, activity_type) is the primary key (combination of columns with unique values) of this table.
machine_id is the ID of a machine.
process_id is the ID of a process running on the machine with ID machine_id.
activity_type is an ENUM (category) of type (&#39;start&#39;, &#39;end&#39;).
timestamp is a float representing the current time in seconds.
&#39;start&#39; means the machine starts the process at the given timestamp and &#39;end&#39; means the machine ends the process at the given timestamp.
The &#39;start&#39; timestamp will always be before the &#39;end&#39; timestamp for every (machine_id, process_id) pair.
It is guaranteed that each (machine_id, process_id) pair has a &#39;start&#39; and &#39;end&#39; timestamp.


 


There is a factory website that has several machines each running the **same number of processes**. Write a solution to find the **average time** each machine takes to complete a process.


The time to complete a process is the `&#39;end&#39; timestamp` minus the `&#39;start&#39; timestamp`. The average time is calculated by the total time to complete every process on the machine divided by the number of processes that were run.


The resulting table should have the `machine_id` along with the **average time** as `processing_time`, which should be **rounded to 3 decimal places**.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Activity table:
+------------+------------+---------------+-----------+
| machine_id | process_id | activity_type | timestamp |
+------------+------------+---------------+-----------+
| 0          | 0          | start         | 0.712     |
| 0          | 0          | end           | 1.520     |
| 0          | 1          | start         | 3.140     |
| 0          | 1          | end           | 4.120     |
| 1          | 0          | start         | 0.550     |
| 1          | 0          | end           | 1.550     |
| 1          | 1          | start         | 0.430     |
| 1          | 1          | end           | 1.420     |
| 2          | 0          | start         | 4.100     |
| 2          | 0          | end           | 4.512     |
| 2          | 1          | start         | 2.500     |
| 2          | 1          | end           | 5.000     |
+------------+------------+---------------+-----------+
**Output:** 
+------------+-----------------+
| machine_id | processing_time |
+------------+-----------------+
| 0          | 0.894           |
| 1          | 0.995           |
| 2          | 1.456           |
+------------+-----------------+
**Explanation:** 
There are 3 machines running 2 processes each.
Machine 0&#39;s average time is ((1.520 - 0.712) + (4.120 - 3.140)) / 2 = 0.894
Machine 1&#39;s average time is ((1.550 - 0.550) + (1.420 - 0.430)) / 2 = 0.995
Machine 2&#39;s average time is ((4.512 - 4.100) + (5.000 - 2.500)) / 2 = 1.456

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT 
    s.machine_id,
    ROUND(AVG(e.timestamp - s.timestamp), 3) AS processing_time
FROM Activity s
JOIN Activity e
    ON s.machine_id = e.machine_id
   AND s.process_id = e.process_id
WHERE s.activity_type = 'start'
  AND e.activity_type = 'end'
GROUP BY s.machine_id;

```

---

## 🧪 Sample Test Case

```
{"headers":{"Activity":["machine_id","process_id","activity_type","timestamp"]},"rows":{"Activity":[[0,0,"start",0.712],[0,0,"end",1.52],[0,1,"start",3.14],[0,1,"end",4.12],[1,0,"start",0.55],[1,0,"end",1.55],[1,1,"start",0.43],[1,1,"end",1.42],[2,0,"start",4.1],[2,0,"end",4.512],[2,1,"start",2.5],[2,1,"end",5]]}}
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
