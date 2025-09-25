# Day 16: Subqueries in SQL

---

## 1. Highest-paid employee in each department (using subqueries)
```
SELECT department_id, name, salary
FROM employees
WHERE salary = (
SELECT MAX(salary)
FROM employees e2
WHERE e2.department_id = employees.department_id
);
```
*Finds the top earner for each department.*

---

## 2. Customers who placed more orders than average (using subqueries)
```
SELECT customer_id, name
FROM customers
WHERE (
SELECT COUNT()
FROM orders
WHERE orders.customer_id = customers.customer_id
) > (
SELECT AVG(order_count)
FROM (
SELECT COUNT() AS order_count
FROM orders
GROUP BY customer_id
) sub
);
```
*Returns customers with more-than-average order counts.*

---

## 3. Employees earning more than department average salary
```
SELECT name, salary, department_id
FROM employees
WHERE salary >
(SELECT AVG(salary)
FROM employees e2
WHERE e2.department_id = employees.department_id);
```
*Lists employees whose salary is above their department’s average.*

---

## 4. Products with a price above the average
```
SELECT product_id, product_name, price
FROM products
WHERE price > (SELECT AVG(price) FROM products);
```
*Products priced above overall mean price.*

---

## 5. Orders with total value above average
```
SELECT order_id, customer_id, total_value
FROM orders
WHERE total_value > (SELECT AVG(total_value) FROM orders);
```
*Finds orders whose total is higher than the general order average.*

---
