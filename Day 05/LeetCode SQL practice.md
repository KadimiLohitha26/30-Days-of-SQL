# Day 05: LeetCode 620 - Not Boring Movies

---

## Question

Table: Cinema

| Column Name  | Type    |
|--------------|---------|
| id           | int     |
| movie        | varchar |
| description  | varchar |
| rating       | float   |

Write a SQL query to report all movies with:
- an **odd-numbered id**
- a `description` that is **not 'boring'**

Return the result table **ordered by rating in descending order**.

---

## SQL Solution
```
SELECT *
FROM Cinema
WHERE MOD(id, 2) = 1
AND description != 'boring'
ORDER BY rating DESC;
```
# LeetCode 1729 - Find Followers Count

---

## Question

Table: Followers

| Column Name  | Type |
|--------------|------|
| user_id      | int  |
| follower_id  | int  |

(user_id, follower_id) is the primary key for this table.

Write an SQL query to return, for each user, the number of followers.  
Return the result table ordered by user_id in ascending order.

**Example Input:**

| user_id | follower_id |
|---------|-------------|
| 0       | 1           |
| 1       | 0           |
| 2       | 0           |
| 2       | 1           |

**Expected Output:**

| user_id | followers_count |
|---------|----------------|
| 0       | 1              |
| 1       | 1              |
| 2       | 2              |

---

## SQL Solution
```
SELECT user_id, COUNT(follower_id) AS followers_count
FROM Followers
GROUP BY user_id
ORDER BY user_id ASC;
```
