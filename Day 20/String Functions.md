# Day 20: SQL String Functions Practice

---

## 1. Convert all names in a customers table to uppercase
```
SELECT UPPER(name) AS upper_name
FROM customers;
```
*Returns all names in uppercase.*

---

## 2. Extract the first 3 characters of a product_code column from a products table
```
SELECT SUBSTRING(product_code, 1, 3) AS first_three_chars
FROM products;
```
*Gets the first three letters of each product code.*

---

## 3. Replace all spaces in an address column with underscores
```
SELECT REPLACE(address, ' ', '_') AS updated_address
FROM customers;
```
*Replaces every space in the address string with an underscore.*

---

## 4. Find the position of the first occurrence of '@' in an email column
```
SELECT POSITION('@' IN email) AS at_position
FROM customers;
```
*Shows where '@' first appears in the email text (1-based index).*

---

## 5. Reverse the text in a comments column
```
SELECT REVERSE(comments) AS reversed_comments
FROM reviews;
```
*Flips the text of each comment for the reviews table.*

---
