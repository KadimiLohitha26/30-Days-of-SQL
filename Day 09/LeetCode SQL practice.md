# Day 09: LeetCode SQL Practice

---

## 1. LeetCode 183 - Customers Who Never Order

**Table Structure**

Customers

| id | name  |
|----|-------|
| 1  | Joe   |
| 2  | Henry |
| 3  | Sam   |
| 4  | Max   |

Orders

| id | customerId |
|----|------------|
| 1  | 3          |
| 2  | 1          |

### Question  
Find all customers who never order anything.

### Solution

```
SELECT name AS Customers
FROM Customers
WHERE id NOT IN (SELECT customerId FROM Orders);
```
---

## Expected Output

| Customers |
|-----------|
| Henry     |
| Max       |

---
# LeetCode 586 – Customer Placing the Largest Number of Orders

---

## Table: Orders

| order_number | customer_number |
|--------------|----------------|
| 1            | 1              |
| 2            | 2              |
| 3            | 3              |
| 4            | 3              |

---

## Question

Find the customer_number for the customer who has placed the largest number of orders.

---



### Solution
```
SELECT customer_number
FROM Orders
GROUP BY customer_number
ORDER BY COUNT(*) DESC
LIMIT 1;
```


## Expected Output

| customer_number |
|-----------------|
| 3               |

---



