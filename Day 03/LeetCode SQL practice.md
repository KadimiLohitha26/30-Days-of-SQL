# Day 03: LeetCode 595 - Big Countries

---

## Question

A country is big if it has an area of at least 3,000,000 square km or a population of at least 25,000,000.  
Write an SQL query to find the name, population, and area of the big countries.  
Return the result table in any order.

**Table: World**

| name        | continent | area    | population | gdp      |
|-------------|-----------|---------|------------|----------|
| Afghanistan | Asia      | 652230  | 25500100   | 20343000 |
| Algeria     | Africa    | 2381741 | 37100000   | 188681000|
| ...         | ...       | ...     | ...        | ...      |

---

## SQL Solution
````
SELECT name, population, area
FROM World
WHERE area >= 3000000
OR population >= 25000000;
````
# LeetCode 584 - Find Customer Referee

---

## Table: Customer

| Column Name | Type    |
|-------------|---------|
| id          | int     |
| name        | varchar |
| referee_id  | int     |

- `id` is the primary key for this table.
- Each row indicates the id of a customer, their name, and the id of the customer who referred them.



## Question

Find the names of the customers that are either:
1. **Referred by any customer with** `id != 2`.
2. **Not referred by any customer** (i.e., `referee_id IS NULL`).

Return the result table in any order.

---


## SQL Solution
````
SELECT name
FROM Customer
WHERE referee_id <> 2 OR referee_id IS NULL;
````

