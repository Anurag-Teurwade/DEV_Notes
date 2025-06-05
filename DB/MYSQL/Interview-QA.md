
# 📘 MySQL Interview Questions & Answers 

## 🔹 Basic Questions (1–25)

### 1. What is MySQL?
MySQL is a free, open-source relational database management system used to store and manage data.

### 2. What is SQL?
SQL (Structured Query Language) is the language used to communicate with databases like MySQL.

### 3. What is the difference between SQL and MySQL?
- SQL is the language
- MySQL is the database software that uses SQL

### 4. What is the default port of MySQL?
Port **3306**

### 5. How do you create a database in MySQL?
```sql
CREATE DATABASE myDatabase;
```

### 6. How do you delete a database?
```sql
DROP DATABASE myDatabase;
```

### 7. What is a table in MySQL?
A table is where data is stored in rows and columns.

### 8. How do you create a table?
```sql
CREATE TABLE students (
  id INT,
  name VARCHAR(50)
);
```

### 9. What is a primary key?
A column that uniquely identifies each row. Example: `id`.

### 10. What is the use of AUTO_INCREMENT?
It automatically increases the value of a column (usually `id`) when a new row is inserted.

### 11. What is the difference between WHERE and HAVING?
- `WHERE` filters **rows** before grouping
- `HAVING` filters **groups** after `GROUP BY`

### 12. What is a JOIN?
A JOIN is used to combine rows from two or more tables based on a related column.

### 13. What is INNER JOIN?
Returns only matching rows from both tables.

### 14. What is LEFT JOIN?
Returns all rows from the left table, and matched rows from the right table.

### 15. What is a constraint in MySQL?
A rule applied to a column (e.g., NOT NULL, UNIQUE).

### 16. What is a UNIQUE constraint?
Ensures all values in a column are different.

### 17. What is a FOREIGN KEY?
A key that links one table to another.

### 18. How to insert data into a table?
```sql
INSERT INTO students (id, name) VALUES (1, 'Anurag');
```

### 19. How to update a record in a table?
```sql
UPDATE students SET name='Rahul' WHERE id=1;
```

### 20. How to delete a record?
```sql
DELETE FROM students WHERE id=1;
```

### 21. What is the use of SELECT?
It is used to read/fetch data from a table.

### 22. How to fetch only unique records?
Use `DISTINCT`:
```sql
SELECT DISTINCT name FROM students;
```

### 23. How to get the current date and time?
```sql
SELECT NOW();
```

### 24. What is a VIEW?
A virtual table based on the result of a SQL query.

### 25. What is indexing?
It makes searching data faster.

---

## 🔹 Tricky / Conceptual Questions (26–50)

### 26. Difference between DELETE, TRUNCATE, and DROP?
| Command  | Description | Rollback Possible | Resets Auto-increment |
|----------|-------------|--------------------|-----------------------|
| DELETE   | Removes rows | Yes                | No                    |
| TRUNCATE | Removes all  | No                 | Yes                   |
| DROP     | Deletes table| No                 | -                     |

### 27. What is normalization?
Organizing data to reduce redundancy (repeated data).

### 28. What is denormalization?
Opposite of normalization — used to improve performance by allowing some redundancy.

### 29. What is a subquery?
A query inside another query.

### 30. What is a stored procedure?
A saved group of SQL statements that can be reused.

### 31. What is a trigger?
Code that runs automatically when something happens in the table (like insert, delete, update).

### 32. What is a transaction?
A group of SQL statements that are executed together. Either all succeed or all fail.

### 33. What are ACID properties?
- **A**tomicity
- **C**onsistency  
- **I**solation
- **D**urability  
These make transactions reliable.

### 34. What is the use of LIMIT in MySQL?
Restricts the number of rows returned.
```sql
SELECT * FROM students LIMIT 5;
```

### 35. What is the BETWEEN operator?
Used to filter a range:
```sql
SELECT * FROM students WHERE id BETWEEN 5 AND 10;
```

### 36. How to count records in a table?
```sql
SELECT COUNT(*) FROM students;
```

### 37. How to rename a column in MySQL?
```sql
ALTER TABLE students CHANGE name full_name VARCHAR(50);
```

### 38. What is the difference between CHAR and VARCHAR?
- `CHAR`: fixed length
- `VARCHAR`: variable length

### 39. How to check the MySQL version?
```sql
SELECT VERSION();
```

### 40. What are aggregate functions?
Functions that do a calculation on a set of values: `SUM()`, `AVG()`, `COUNT()`, `MAX()`, `MIN()`.

### 41. What is the default storage engine in MySQL?
InnoDB (supports transactions and foreign keys).

### 42. How to add a new column?
```sql
ALTER TABLE students ADD age INT;
```

### 43. How to remove a column?
```sql
ALTER TABLE students DROP COLUMN age;
```

### 44. What is the use of IFNULL()?
Returns a value if the column is `NULL`.
```sql
SELECT IFNULL(name, 'Unknown') FROM students;
```

### 45. How to find the highest salary (or any max value)?
```sql
SELECT MAX(salary) FROM employees;
```

### 46. How to sort data?
```sql
SELECT * FROM students ORDER BY name ASC;
```

### 47. What is the difference between IS NULL and = NULL?
Use `IS NULL`, not `= NULL`.

### 48. What is a composite key?
A primary key using more than one column.

### 49. Can we have two primary keys in a table?
No, only one primary key per table, but it can be composite (multiple columns).

### 50. What is a schema in MySQL?
A schema is like a database — it holds tables, views, etc.

