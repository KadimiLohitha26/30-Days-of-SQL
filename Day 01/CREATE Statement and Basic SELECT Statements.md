# Day 01: CREATE Statement and Basic SELECT Statements

## CREATE TABLE Statement Example
## Create the products table

```
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(50) NOT NULL,
    price DECIMAL(10, 2),
    stock_quantity INT
);
```
Basic SELECT Statements Examples

### 1. Insert Sample Data into the `students` table:
```
INSERT INTO students (id, name, age, department) VALUES
(1, 'John Doe', 30, 'HR'),
(2, 'Jane Smith', 25, 'IT'),
(3, 'Sam Brown', 35, 'Marketing');
```
### 2. Select Specific Columns from the `employees` table:
```
SELECT name, department FROM employees;
```

### 3. Select All Rows from the `students` table:
```

SELECT * FROM students;
```
## 4. Retrieve employees aged above 30
```
SELECT * FROM employees
WHERE age > 30;
```
## 5. Retrieve employees in the IT or Marketing department
```
SELECT * FROM employees
WHERE department = 'IT' OR department = 'Marketing';
```
## 6. Retrieve employees NOT in the HR department
```
SELECT * FROM employees
WHERE department <> 'HR';
```
