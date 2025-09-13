# Day 04: ORDER BY Clause Practice

---

## 1. Retrieve all rows from the `employees` table and sort them by `name` in ascending order
```
SELECT * FROM employees
ORDER BY name ASC;
```
---

## 2. Sort the `employees` table by `department` in descending order
```
SELECT * FROM employees
ORDER BY department DESC;
```
---

## 3. Combine sorting by `age` in ascending order and `department` in alphabetical order
```
SELECT * FROM employees
ORDER BY age ASC, department ASC;
```
---

## 4. Sort the `products` table by `price` in descending order and `stock_quantity` in ascending order
```
SELECT * FROM products
ORDER BY price DESC, stock_quantity ASC;
```
---

## 5. Display all customers sorted by their country and then by their name (ascending)
```
SELECT * FROM customers
ORDER BY country ASC, name ASC;
```

---

## 6. Show all students ordered first by grade (descending) and then by age (ascending)
```

SELECT * FROM students
ORDER BY grade DESC, age ASC;
```

