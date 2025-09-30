# Day 21: SQL Date & Time Functions Practice

---

## 1. Find the day of the week for the date 2024-12-25
```
SELECT DAYNAME('2024-12-25') AS day_of_week;
```
*Returns the weekday for December 25, 2024 (e.g., 'Wednesday').*

---

## 2. Calculate the number of days between your birthday and today
```
SELECT DATEDIFF(CURRENT_DATE, '2003-03-30') AS days_difference;
```
*Shows the number of days since 30 March 2003 (update to your actual birthday if different).*

---

## 3. Add 3 months to the current date and display the result
```
SELECT DATE_ADD(CURRENT_DATE, INTERVAL 3 MONTH) AS plus_3months;
```
*Adds three calendar months to today's date.*

---

## 4. Extract the year, month, and day from the timestamp 2023-11-15 08:45:30
```
SELECT
EXTRACT(YEAR FROM TIMESTAMP '2023-11-15 08:45:30') AS year,
EXTRACT(MONTH FROM TIMESTAMP '2023-11-15 08:45:30') AS month,
EXTRACT(DAY FROM TIMESTAMP '2023-11-15 08:45:30') AS day;
```
*Separates the timestamp components.*

---

## 5. Format the current date in the pattern: DD-MM-YYYY
```
SELECT DATE_FORMAT(CURRENT_DATE, '%d-%m-%Y') AS formatted_date;
```
*Shows today’s date in DD-MM-YYYY format.*

---


