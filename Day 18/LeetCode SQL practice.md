# Day 18: LeetCode 176 - Second Highest Salary

---

## Table Structure

**Employee**

| id | salary |
|----|--------|
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |

---

## Question

Write a SQL query to find the second highest distinct salary from the Employee table.  
If there is no second highest salary, return NULL.

---

## SQL Solution (LIMIT/OFFSET approach)
```
SELECT 
    (SELECT DISTINCT salary
     FROM Employee
     ORDER BY salary DESC
     LIMIT 1 OFFSET 1) AS SecondHighestSalary;
```   
---

## Expected Output

**Example 1**

| SecondHighestSalary |
|---------------------|
| 200                 |

**Example 2 (only one salary)**

| SecondHighestSalary |
|---------------------|
| NULL                |

---

#LeetCode 607 - Sales Person

---

## Table Structures

**SalesPerson**

| sales_id | name  | ... |
|----------|-------|-----|
| 1        | John  |     |
| 2        | Amy   |     |
| 3        | Mark  |     |
| 4        | Pam   |     |
| 5        | Alex  |     |

**Company**

| com_id | name   | ...  |
|--------|--------|------|
| 1      | RED    |      |
| 2      | ORANGE |      |
| 3      | YELLOW |      |
| 4      | GREEN  |      |

**Orders**

| order_id | order_date | com_id | sales_id |
|----------|------------|--------|----------|
| 1        | ...        | 1      | 1        |
| 2        | ...        | 2      | 1        |
| 3        | ...        | 3      | 2        |
| 4        | ...        | 4      | 3        |

---

## Question

Write a solution to find the names of all the salespersons who did not have any orders related to the company with the name "RED".

---

## SQL Solution
```
SELECT s.name
FROM SalesPerson s
WHERE s.sales_id NOT IN (
SELECT o.sales_id
FROM Orders o
JOIN Company c ON o.com_id = c.com_id
WHERE c.name = 'RED'
);
```

---

## Expected Output

| name |
|------|
| Amy  |
| Mark |
| Alex |

---

