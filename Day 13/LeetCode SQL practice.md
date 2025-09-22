# Day 13: LeetCode 196 - Delete Duplicate Emails

---

## Table Structure

**Person**

| id | email           |
|----|-----------------|
| 1  | john@example.com|
| 2  | bob@example.com |
| 3  | john@example.com|
| 4  | emily@example.com|
| 5  | phil@example.com|
| 6  | bob@example.com |

---

## Question

Write a SQL query to delete all duplicate emails, keeping only one unique email with the smallest id. The table should be modified in-place.

---

## SQL Solution (Self Join Delete)
```
DELETE p1
FROM Person p1
INNER JOIN Person p2
ON p1.email = p2.email AND p1.id > p2.id;
```

*Explanation:* This deletes rows with duplicate emails having larger id values, keeping the row with the smallest id for each email.

---

---

## Expected Final Table

| id | email           |
|----|-----------------|
| 1  | john@example.com|
| 2  | bob@example.com |
| 4  | emily@example.com|
| 5  | phil@example.com |

---

#LeetCode 1050 - Actors and Directors Who Cooperated At Least Three Times

---

## Table Structure

**ActorDirector**

| actor_id | director_id | timestamp |
|----------|-------------|-----------|
| 1        | 1           | 0         |
| 1        | 1           | 1         |
| 1        | 1           | 2         |
| 1        | 2           | 3         |
| 1        | 2           | 4         |
| 2        | 1           | 5         |
| 2        | 1           | 6         |

---

## Question

Find all pairs (actor_id, director_id) where the actor cooperated with the director at least three times.

---

## SQL Solution
```
SELECT actor_id, director_id
FROM ActorDirector
GROUP BY actor_id, director_id
HAVING COUNT(*) >= 3;
```

---

## Expected Output

| actor_id | director_id |
|----------|-------------|
| 1        | 1           |

---



