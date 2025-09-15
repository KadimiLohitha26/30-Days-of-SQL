# Day 06: SQL GROUP BY and Aggregate Functions

This day’s practice covers counting, averaging, summing, min/max, and grouping by single or multiple columns, as well as using HAVING for grouped filtering.

---

## 1. Find the total number of students in each course
```
SELECT course, COUNT(*) AS total_students
FROM students
GROUP BY course;
```
---

## 2. Calculate the average salary of employees in each department
```
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department;
```
---

## 3. Find the minimum and maximum price of products in each category
```
SELECT category, MIN(price) AS min_price, MAX(price) AS max_price
FROM products
GROUP BY category;
```
---

## 4. Count the number of orders placed by each customer
```
SELECT customer_id, COUNT(*) AS order_count
FROM orders
GROUP BY customer_id;
```
---

## 5. Find the total sales amount for each product
```
SELECT product_id, SUM(amount) AS total_sales
FROM sales
GROUP BY product_id;
```
---

## 6. Show the average marks of students in each combination of subject and grade
```
SELECT subject, grade, AVG(marks) AS average_marks
FROM students
GROUP BY subject, grade;
```
---

## 7. Display the number of products for each category and supplier
```
SELECT category, supplier_id, COUNT(*) AS product_count
FROM products
GROUP BY category, supplier_id;
```
