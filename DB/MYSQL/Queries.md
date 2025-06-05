# 🐬 Complete MySQL Queries and Meanings


## 🟣 1. Database Basics

```sql
CREATE DATABASE college;
-- Creates a new database named 'college'

USE college;
-- Selects the 'college' database for use

CREATE TABLE students (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  age INT,
  admission_date DATE
);
-- Creates a table named 'students' with columns and a primary key

DESCRIBE students;
-- Displays the structure of the 'students' table
```

---

## 🟠 2. CRUD Operations

```sql
-- INSERT
INSERT INTO students (name, age, admission_date)
VALUES ('John Doe', 20, '2024-06-01');
-- Adds a new student record

-- SELECT
SELECT * FROM students;
-- Retrieves all data from the table

-- UPDATE
UPDATE students SET age = 21 WHERE name = 'John Doe';
-- Updates the age of 'John Doe'

-- DELETE
DELETE FROM students WHERE name = 'John Doe';
-- Deletes the student record for 'John Doe'
```

---

## 🟡 3. Constraints

```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  username VARCHAR(50) UNIQUE,
  email VARCHAR(100) NOT NULL
);
-- Creates a table with PRIMARY KEY, UNIQUE, and NOT NULL constraints
```

---

## 🟢 4. SQL Clauses

```sql
SELECT * FROM students WHERE age > 18;
-- Filters students older than 18

SELECT * FROM students ORDER BY name ASC;
-- Sorts records by name

SELECT age, COUNT(*) FROM students GROUP BY age;
-- Groups by age and counts students

SELECT age, COUNT(*) FROM students GROUP BY age HAVING COUNT(*) > 1;
-- Same as above, but filters groups

SELECT * FROM students LIMIT 5;
-- Returns first 5 records

SELECT DISTINCT age FROM students;
-- Returns unique ages

SELECT * FROM students WHERE age BETWEEN 18 AND 22;
-- Returns students aged between 18 and 22

SELECT * FROM students WHERE name IN ('John', 'Jane');
-- Returns students with names John or Jane

SELECT * FROM students WHERE name LIKE 'J%';
-- Returns names starting with 'J'
```

---

## 🔵 5. Joins

```sql
-- INNER JOIN
SELECT s.name, d.name FROM students s
INNER JOIN departments d ON s.dept_id = d.id;
-- Returns matching rows from both tables

-- LEFT JOIN
SELECT s.name, d.name FROM students s
LEFT JOIN departments d ON s.dept_id = d.id;
-- All students + department if available

-- RIGHT JOIN
SELECT s.name, d.name FROM students s
RIGHT JOIN departments d ON s.dept_id = d.id;
-- All departments + students if available

-- FULL OUTER JOIN (simulated)
SELECT s.name, d.name FROM students s
LEFT JOIN departments d ON s.dept_id = d.id
UNION
SELECT s.name, d.name FROM students s
RIGHT JOIN departments d ON s.dept_id = d.id;
-- Combines both

-- SELF JOIN
SELECT A.name, B.name FROM students A, students B WHERE A.id != B.id;
-- Pairs of students

-- CROSS JOIN
SELECT A.name, B.name FROM students A CROSS JOIN departments B;
-- All combinations of students and departments
```

---

## 🟣 6. Functions

```sql
-- String Functions
SELECT CONCAT('Hello', ' ', 'World');
SELECT LENGTH('MySQL');
SELECT SUBSTRING('MySQL', 1, 3);

-- Numeric Functions
SELECT ROUND(5.678, 2);
SELECT CEIL(5.1);
SELECT FLOOR(5.9);

-- Date Functions
SELECT NOW();
SELECT CURDATE();
SELECT DATEDIFF('2025-01-01', '2024-01-01');

-- Aggregate Functions
SELECT COUNT(*) FROM students;
SELECT AVG(age) FROM students;
SELECT MAX(age), MIN(age) FROM students;
```

---

## 🟠 7. Subqueries

```sql
-- Single Row
SELECT name FROM students WHERE age = (SELECT MAX(age) FROM students);

-- Multi Row
SELECT name FROM students WHERE age IN (SELECT age FROM students WHERE age > 20);

-- Correlated
SELECT name FROM students s WHERE age > (SELECT AVG(age) FROM students WHERE dept_id = s.dept_id);
```

---

## 🟡 8. Views

```sql
CREATE VIEW young_students AS SELECT * FROM students WHERE age < 21;
-- Creates a view

ALTER VIEW young_students AS SELECT name FROM students WHERE age < 21;
-- Updates the view

DROP VIEW young_students;
-- Deletes the view
```

---

## 🟢 9. Indexes

```sql
CREATE INDEX idx_name ON students(name);
-- Creates an index on name

CREATE INDEX idx_age_name ON students(age, name);
-- Composite index

DROP INDEX idx_name ON students;
-- Removes the index
```

---

## 🔵 10. Stored Procedures & Functions

```sql
DELIMITER //
CREATE PROCEDURE GetAllStudents()
BEGIN
  SELECT * FROM students;
END;
//

CALL GetAllStudents();
-- Calls the procedure
```

---

## 🟣 11. Triggers

```sql
CREATE TRIGGER before_insert_student
BEFORE INSERT ON students
FOR EACH ROW
SET NEW.admission_date = CURDATE();
-- Sets default date on insert
```

---

## 🟠 12. Transactions & ACID

```sql
START TRANSACTION;
UPDATE students SET age = age + 1 WHERE age < 25;
COMMIT;
-- Commits changes

ROLLBACK;
-- Undoes last transaction

SAVEPOINT sp1;
-- Creates a savepoint
```

---

## 🟡 13. User Management & Security

```sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON college.* TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
-- Adds user and grants access
```

---

## 🟢 14. Backup and Restore

```bash
mysqldump -u root -p college > backup.sql
-- Backs up database

mysql -u root -p college < backup.sql
-- Restores database
```

---

## 🔵 15. Performance Tuning & Optimization

```sql
EXPLAIN SELECT * FROM students WHERE age > 18;
-- Shows query execution plan
```

---

## 🟣 16. MySQL with Programming Languages
(No SQL queries — connection scripts depend on language)

---

## 🟠 17. MySQL Workbench
(Visual Tools — no SQL queries required)

---

## 🟡 28. Advanced Concepts

```sql
-- Partitioning (Example)
CREATE TABLE logs (
  id INT,
  log_date DATE
) PARTITION BY RANGE(YEAR(log_date)) (
  PARTITION p2023 VALUES LESS THAN (2024),
  PARTITION p2024 VALUES LESS THAN (2025)
);

-- Event Scheduler
CREATE EVENT update_age
ON SCHEDULE EVERY 1 DAY
DO
  UPDATE students SET age = age + 1 WHERE name = 'Auto';
```
