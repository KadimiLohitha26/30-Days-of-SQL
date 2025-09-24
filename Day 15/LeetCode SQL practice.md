# Day 15: LeetCode 1075 - Project Employees I

---

## Table Structures

**Project**

| project_id | employee_id |
|------------|-------------|
| 1          | 1           |
| 1          | 2           |
| 1          | 3           |
| 2          | 1           |
| 2          | 4           |

**Employee**

| employee_id | name  | experience_years |
|-------------|-------|------------------|
| 1           | Khaled| 3                |
| 2           | Ali   | 2                |
| 3           | John  | 1                |
| 4           | Doe   | 2                |

---

## Question

Write an SQL query that reports the average experience years of all the employees for each project, rounded to 2 digits.  
Return the result table in any order.

---

## SQL Solution
```

SELECT p.project_id,
ROUND(AVG(e.experience_years), 2) AS average_years
FROM Project p
JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY p.project_id;
```

---

## Expected Output

| project_id | average_years |
|------------|---------------|
| 1          | 2.00          |
| 2          | 2.50          |

---

#LeetCode 1084 - Sales Analysis III

---

## Table Structures

**Product**

| product_id | product_name |
|------------|-------------|
| 1          | S8          |
| 2          | G4          |
| 3          | iPhone      |

**Sales**

| sale_id | product_id | sale_date  |
|---------|------------|------------|
| 1       | 1          | 2019-01-21 |
| 2       | 1          | 2019-02-17 |
| 7       | 2          | 2019-03-30 |

---

## Question

Report the products that were only sold in the first quarter of 2019 (between 2019-01-01 and 2019-03-31, inclusive).

---

## SQL Solution
```

SELECT p.product_id, p.product_name
FROM Product p
JOIN Sales s ON p.product_id = s.product_id
GROUP BY p.product_id, p.product_name
HAVING MIN(s.sale_date) >= '2019-01-01'
AND MAX(s.sale_date) <= '2019-03-31';
```
---

## Expected Output

| product_id | product_name |
|------------|-------------|
| 1          | S8          |

---


