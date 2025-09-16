# Day 07: LeetCode 181 - Employees Earning More Than Their Managers

---

## Question

Table: Employee

| id | name  | salary | managerId |
|----|-------|--------|-----------|
| 1  | Joe   | 70000  | 3         |
| 2  | Henry | 80000  | 4         |
| 3  | Sam   | 60000  | null      |
| 4  | Max   | 90000  | null      |

Write an SQL query to find the names of employees who earn more than their managers.  
Return the result table in any order.

---

## SQL Solution
```
SELECT e1.name as Employee
FROM Employee e1 
JOIN Employee e2
    ON e1.managerId=e2.id
WHERE e1.salary>e2.salary
```
# LeetCode 182 - Duplicate Emails

---

## Question

Table: Person

| id | email     |
|----|-----------|
| 1  | a@b.com   |
| 2  | c@d.com   |
| 3  | a@b.com   |

Write an SQL query to report all duplicate emails.  
Return the result table in any order.

**Expected Output**  
| Email   |
|---------|
| a@b.com |

---

## SQL Solution
```
SELECT email AS Email
FROM person
GROUP BY email
HAVING count(*)>1
```
