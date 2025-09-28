# DAY 19- Set Operations and UNION/INTERSECT

---

## 1. Find all unique customers who placed orders in either year
```
SELECT customer_id FROM orders_2023
UNION
SELECT customer_id FROM orders_2024;
```
*Returns one record per unique customer across both years.*

---

## 2. Find customers who placed orders in both orders_2023 and orders_2024
```
SELECT customer_id FROM orders_2023
INTERSECT
SELECT customer_id FROM orders_2024;
```
*Lists customers who were active in both years.*

---

## 3. Retrieve products listed in products_2023 but not in products_2024
```
SELECT product_id FROM products_2023
EXCEPT
SELECT product_id FROM products_2024;
```
*Finds products discontinued or not present in the next year's table.*

---

## 4. Combine two sales tables and include duplicate entries
```
SELECT * FROM sales_2023
UNION ALL
SELECT * FROM sales_2024;
```
*Includes every row from both years—duplicates are retained.*

---

## 5. Find employees who work in two specific projects using INTERSECT
```
SELECT employee_id FROM project_employee WHERE project_id = 1
INTERSECT
SELECT employee_id FROM project_employee WHERE project_id = 2;
```
*Lists employees assigned to both projects at once.*

---
