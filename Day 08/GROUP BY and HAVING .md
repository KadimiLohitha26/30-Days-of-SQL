# Day 08: SQL GROUP BY and HAVING Practice

---

## 1. Find customers whose total order value exceeds $5000 (orders table)
```

SELECT customer_id, SUM(order_total) AS total_spent
FROM orders
GROUP BY customer_id
HAVING SUM(order_total) > 5000;
```
---

## 2. Filter products where the average price is greater than $50 (products table)
```
SELECT product_name, AVG(price) AS average_price
FROM products
GROUP BY product_name
HAVING AVG(price) > 50;
```
---

## 3. Additional: Only include products with more than 10 units sold and avg price above $50
```
SELECT product_name, COUNT() AS items_sold, AVG(price) AS average_price
FROM products
GROUP BY product_name
HAVING AVG(price) > 50 AND COUNT() > 10;
```
---

## 4. Find authors with more than 3 published books and an average rating above 4.5 (library table)
```
SELECT author, COUNT() AS books_published, AVG(rating) AS average_rating
FROM library
GROUP BY author
HAVING COUNT() > 3 AND AVG(rating) > 4.5;
```
---

## 5. Find departments where the total salary of employees exceeds $100,000 (company table)
```
SELECT department, SUM(salary) AS total_salary
FROM company
GROUP BY department
HAVING SUM(salary) > 100000;
```
