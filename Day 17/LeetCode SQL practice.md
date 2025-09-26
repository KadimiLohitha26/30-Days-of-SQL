# Day 17: LeetCode 511 - Game Play Analysis I

---

## Table Structure

**Activity**

| player_id | device_id | event_date  | games_played |
|-----------|-----------|-------------|--------------|
| 1         | 2         | 2016-03-01  | 5            |
| 1         | 2         | 2016-05-02  | 6            |
| 2         | 3         | 2017-06-25  | 1            |
| 3         | 1         | 2016-03-02  | 0            |
| 3         | 4         | 2018-07-03  | 5            |

---

## Question

Write a solution to find the first login date for each player.

---

## SQL Solution
```

SELECT player_id, MIN(event_date) AS first_login
FROM Activity
GROUP BY player_id;
```

---

## Expected Output

| player_id | first_login |
|-----------|-------------|
| 1         | 2016-03-01  |
| 2         | 2017-06-25  |
| 3         | 2016-03-02  |

---
# LeetCode 577 - Employee Bonus

---

## Table Structures

**Employee**

| empId | name   | supervisor | salary |
|-------|--------|------------|--------|
| 1     | John   | 3          | 1000   |
| 2     | Dan    | 3          | 2000   |
| 3     | Brad   | NULL       | 4000   |
| 4     | Thomas | 3          | 4000   |

**Bonus**

| empId | bonus |
|-------|-------|
| 2     | 500   |
| 4     | 2000  |

---

## Question

Write a query to report the name and bonus amount of each employee with a bonus less than 1000 or without any bonus at all.

---

## SQL Solution
```
SELECT e.name, b.bonus
FROM Employee e
LEFT JOIN Bonus b ON e.empId = b.empId
WHERE b.bonus < 1000 OR b.bonus IS NULL;
```

---

## Expected Output

| name   | bonus |
|--------|-------|
| John   | NULL  |
| Dan    | 500   |
| Brad   | NULL  |

---

