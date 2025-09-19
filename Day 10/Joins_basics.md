# Day 10: SQL Joins Practice Exercises 🔧


---

## 1. Find all orders with their customer names using an INNER JOIN
```
SELECT o.order_id, o.order_date, c.name AS customer_name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.customer_id;
```
*Shows only those orders that have a matching customer record.*

---

## 2. Use a LEFT JOIN to list all products and their orders from products and orders tables
```

SELECT p.product_id, p.product_name, o.order_id, o.order_date
FROM products p
LEFT JOIN orders o ON p.product_id = o.product_id;
```
*Lists all products, showing order info where available (NULL if not ordered).*

---

## 3. Find departments without any employees using a RIGHT JOIN
```

SELECT d.department_id, d.department_name
FROM employees e
RIGHT JOIN departments d ON e.department_id = d.department_id
WHERE e.employee_id IS NULL;
```
*Displays departments that have no assigned employees.*

---

## 4. List all authors and books they've written using a FULL OUTER JOIN
```
SELECT a.author_id, a.author_name, b.book_id, b.book_title
FROM authors a
FULL OUTER JOIN books b ON a.author_id = b.author_id;
```
*Includes all authors (even those without a book), and all books (even those without a listed author).*

---

## 5. Show employee details with department info, including additional columns
```

SELECT e.employee_id, e.employee_name, e.job_title, d.department_name, d.location
FROM employees e
INNER JOIN departments d ON e.department_id = d.department_id;
```
*Each employee record includes job title and department location.*

---
