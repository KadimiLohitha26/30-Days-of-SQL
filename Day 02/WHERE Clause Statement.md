# Day 02: SQL WHERE Clause

---

## WHERE Clause Statement Examples

---

## Basic Syntax of WHERE
```

SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
---

### 1. Retrieve employees whose names end with the letter `n`:
```
SELECT * FROM employees
WHERE name LIKE '%n';
```

---

### 2. Retrieve employees with non-NULL `age` values:
```
SELECT * FROM employees
WHERE age IS NOT NULL;
```
---

### 3. Retrieve employees whose names start with 'A':
```
SELECT * FROM employees
WHERE name LIKE 'A%';
```
---

### 4. Retrieve employees whose age is between 25 and 35 inclusive:
```
SELECT * FROM employees
WHERE age BETWEEN 25 AND 35;
```
---

### 5. Retrieve employees with names containing 'son':
```
SELECT * FROM employees
WHERE name LIKE '%son%';
```
---

### 6. Retrieve employees whose age is not NULL and greater than 30:
```

SELECT * FROM employees
WHERE age IS NOT NULL AND age > 30;
```
