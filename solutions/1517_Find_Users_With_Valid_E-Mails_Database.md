<div align="center">

# 🗄️ 1517. Find Users With Valid E-Mails

*Pushed on August 04, 2026 · Problem #58 in my journey*

</div>

---

## 📊 Problem Info

| 🏷️ Field             | 📋 Details                |
|----------------------|---------------------------|
| **Difficulty**       | 🟢 Easy |
| **Topic**            | 🗄️ Database   |
| **Time Complexity**  | ⏱️ `O(n)`             |
| **Space Complexity** | 🧠 `O(1)`            |
| **Acceptance Rate**  | ✅ 35.5%              |
| **Language**         | 🔠 MySQL         |

**Tags:** `Database`

---

## 🧩 Problem Description

Table: `Users`



+---------------+---------+
| Column Name   | Type    |
+---------------+---------+
| user_id       | int     |
| name          | varchar |
| mail          | varchar |
+---------------+---------+
user_id is the primary key (column with unique values) for this table.
This table contains information of the users signed up in a website. Some e-mails are invalid.


 


Write a solution to find the users who have **valid emails**.


A valid e-mail has a prefix name and a domain where:



	- **The prefix name** is a string that may contain letters (upper or lower case), digits, underscore `&#39;_&#39;`, period `&#39;.&#39;`, and/or dash `&#39;-&#39;`. The prefix name **must** start with a letter.
	- **The domain** must be exactly `&#39;@leetcode.com&#39;` in lowercase.


Return the result table in **any order**.


The result format is in the following example.


 

<strong class="example">Example 1:**



**Input:** 
Users table:
+---------+-----------+-------------------------+
| user_id | name      | mail                    |
+---------+-----------+-------------------------+
| 1       | Winston   | winston@leetcode.com    |
| 2       | Jonathan  | jonathanisgreat         |
| 3       | Annabelle | bella-@leetcode.com     |
| 4       | Sally     | sally.come@leetcode.com |
| 5       | Marwan    | quarz#2020@leetcode.com |
| 6       | David     | david69@gmail.com       |
| 7       | Shapiro   | .shapo@leetcode.com     |
+---------+-----------+-------------------------+
**Output:** 
+---------+-----------+-------------------------+
| user_id | name      | mail                    |
+---------+-----------+-------------------------+
| 1       | Winston   | winston@leetcode.com    |
| 3       | Annabelle | bella-@leetcode.com     |
| 4       | Sally     | sally.come@leetcode.com |
+---------+-----------+-------------------------+
**Explanation:** 
The mail of user 2 does not have a domain.
The mail of user 5 has the # sign which is not allowed.
The mail of user 6 does not have the leetcode domain.
The mail of user 7 starts with a period.

---

## 💻 My Solution

```sql
# Write your MySQL query statement below
SELECT * FROM Users
WHERE REGEXP_LIKE (mail , '^[A-Za-z][A-Za-z0-9_.-]*@leetcode\\.com$' , 'c');

```

---

## 🧪 Sample Test Case

```
{"headers":{"Users":["user_id","name","mail"]},"rows":{"Users":[[1,"Winston","winston@leetcode.com"],[2,"Jonathan","jonathanisgreat"],[3,"Annabelle","bella-@leetcode.com"],[4,"Sally","sally.come@leetcode.com"],[5,"Marwan","quarz#2020@leetcode.com"],[6,"David","david69@gmail.com"],[7,"Shapiro",".shapo@leetcode.com"]]}}
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
