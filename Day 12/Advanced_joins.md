# Day 12: Advanced SQL Joins & Aggregates

Practice powerful SQL join techniques including self-joins, cross joins, full outer joins, and multi-table joins with aggregates.

---

## 1. Find pairs of employees who share the same manager (Self Join)
```

SELECT e1.employee_id AS employee1_id, e2.employee_id AS employee2_id, e1.manager_id
FROM employees e1
JOIN employees e2
ON e1.manager_id = e2.manager_id
AND e1.employee_id < e2.employee_id;
```

*Finds all unique pairs of employees reporting to the same manager.*

---

## 2. List all products and their orders, including unmatched (Full Outer Join)
```

SELECT p.product_id, p.product_name, o.order_id, o.order_date
FROM products p
FULL OUTER JOIN orders o ON p.product_id = o.product_id;
```
*Shows all products, whether or not they are ordered, and all orders even if they don’t match a product.*

---

## 3. Generate all possible pairs of customers and regions (Cross Join)
```

SELECT c.customer_id, c.customer_name, r.region_id, r.region_name
FROM customers c
CROSS JOIN regions r;
```
*Creates every possible pairing between customers and regions.*

---

## 4. Calculate average order amounts for each product (Join + Aggregate)
```

SELECT p.product_id, p.product_name, AVG(o.amount) AS avg_order_amount
FROM products p
JOIN orders o ON p.product_id = o.product_id
GROUP BY p.product_id, p.product_name;
```
*Shows average sale amount for each ordered product.*

---

## 5. Find detailed order summaries by joining three tables
```

SELECT c.customer_name, p.product_name, o.order_id, o.amount
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
JOIN products p ON o.product_id = p.product_id;
```

*Outputs order summaries, including customer name, product name, order id, and total amount across three tables.*

---

