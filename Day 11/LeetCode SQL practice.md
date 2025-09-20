# Day 11: LeetCode SQL Problems – 175 & 596

---

## 1. LeetCode 175 – Combine Two Tables

### Table Structures

**Person**

| personId | firstName | lastName |
|----------|-----------|----------|
| 1        | John      | Doe      |
| 2        | Jane      | Smith    |
| 3        | Alice     | Brown    |

**Address**

| addressId | personId | city     | state |
|-----------|----------|----------|-------|
| 1         | 1        | New York | NY    |
| 2         | 2        | Boston   | MA    |

---

### Question

Write a solution to report the first name, last name, city, and state of each person in the Person table. If the address of a personId is not present in the Address table, report null instead.

---

### SQL Solution
```

SELECT p.firstName, p.lastName, a.city, a.state
FROM Person p
LEFT JOIN Address a ON a.personId = p.personId;
```

---

### Expected Output

| firstName | lastName | city     | state |
|-----------|----------|----------|-------|
| John      | Doe      | New York | NY    |
| Jane      | Smith    | Boston   | MA    |
| Alice     | Brown    | null     | null  |

---

## 2. LeetCode 596 – Classes With at Least 5 Students

### Table Structure

**Courses**

| student | class |
|---------|-------|
| A       | Math  |
| B       | Math  |
| C       | Math  |
| D       | Math  |
| E       | Math  |
| F       | English |
| G       | English |
| H       | English |
| I       | History |

---

### Question

Write a solution to find all the classes that have at least five students. Return the result table in any order.

---

### SQL Solution
```

SELECT class
FROM Courses
GROUP BY class
HAVING COUNT(student) >= 5;
```

---

### Expected Output

| class |
|-------|
| Math  |

---

These two problems help strengthen concepts for joins and aggregate filtering in SQL.
