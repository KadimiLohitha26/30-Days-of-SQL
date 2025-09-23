# Day 14: LeetCode 1148 & 1068 SQL Problems

---

## 1. LeetCode 1148 - Article Views I

### Table Structure

**Views**

| article_id | author_id | article_title | views |
|------------|-----------|---------------|-------|
| 1          | 101       | SQL Basics    | 100   |
| 2          | 102       | Java Intro   | 150   |
| 1          | 101       | SQL Basics    | 200   |
| 3          | 103       | Python 101   | 250   |

---

### Question

Find all authors that viewed at least one of their own articles. Return the result sorted by author_id ascending.

---

### SQL Solution
```

SELECT DISTINCT author_id AS id
FROM Views
WHERE author_id = viewer_id
ORDER BY id;
```

---

### Expected Output

| id  |
|-----|
| 101 |
| 102 |
| 103 |

---

## 2. LeetCode 1068 - Product Sales Analysis I

### Table Structures

**Sales**

| sale_id | product_id | year | quantity | price |
|---------|------------|------|----------|-------|
| 1       | 100        | 2008 | 10       | 5000  |
| 2       | 100        | 2009 | 12       | 5000  |
| 7       | 200        | 2011 | 15       | 9000  |

**Product**

| product_id | product_name |
|------------|--------------|
| 100        | Nokia        |
| 200        | Apple        |
| 300        | Samsung      |

---

### Question

Write a query to report the product_name, year, and price for each sale_id in Sales table. Return result in any order.

---

### SQL Solution
```

SELECT p.product_name, s.year, s.price
FROM Sales s
INNER JOIN Product p ON s.product_id = p.product_id;
```
---

### Expected Output

| product_name | year | price |
|--------------|------|-------|
| Nokia        | 2008 | 5000  |
| Nokia        | 2009 | 5000  |
| Apple        | 2011 | 9000  |

---


