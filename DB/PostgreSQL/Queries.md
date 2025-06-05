
# 🐘 Complete PostgreSQL Queries and Meanings

---

## 🟣 1. Database Basics

```sql
CREATE DATABASE college;
-- Creates a new database named 'college'

\c college
-- Connects to the 'college' database (in psql shell)

CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  age INT,
  admission_date DATE
);
-- Creates a table named 'students' with auto-increment id and columns

\d students
-- Describes the structure of 'students' table (psql command)
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
-- Retrieves all rows from the table

-- UPDATE
UPDATE students SET age = 21 WHERE name = 'John Doe';
-- Updates age of 'John Doe'

-- DELETE
DELETE FROM students WHERE name = 'John Doe';
-- Deletes the student record for 'John Doe'
```

---

## 🟡 3. Constraints

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  username VARCHAR(50) UNIQUE,
  email VARCHAR(100) NOT NULL
);
-- Creates a table with primary key, unique, and not-null constraints
```

---

## 🟢 4. SQL Clauses

```sql
SELECT * FROM students WHERE age > 18;
-- Get students older than 18

SELECT * FROM students ORDER BY name ASC;
-- Sorts results by name ascending

SELECT age, COUNT(*) FROM students GROUP BY age;
-- Groups students by age and counts them

SELECT age, COUNT(*) FROM students GROUP BY age HAVING COUNT(*) > 1;
-- Groups and filters groups with more than 1 student

SELECT * FROM students LIMIT 5;
-- Returns first 5 rows

SELECT DISTINCT age FROM students;
-- Returns unique ages

SELECT * FROM students WHERE age BETWEEN 18 AND 22;
-- Students aged between 18 and 22

SELECT * FROM students WHERE name IN ('John', 'Jane');
-- Students named John or Jane

SELECT * FROM students WHERE name LIKE 'J%';
-- Names starting with 'J'
```

---

## 🔵 5. Joins

```sql
-- INNER JOIN
SELECT s.name, d.name AS department FROM students s
INNER JOIN departments d ON s.dept_id = d.id;
-- Returns students with matching departments only

-- LEFT JOIN
SELECT s.name, d.name AS department FROM students s
LEFT JOIN departments d ON s.dept_id = d.id;
-- All students + departments if available

-- RIGHT JOIN
SELECT s.name, d.name AS department FROM students s
RIGHT JOIN departments d ON s.dept_id = d.id;
-- All departments + students if available

-- FULL OUTER JOIN
SELECT s.name, d.name AS department FROM students s
FULL OUTER JOIN departments d ON s.dept_id = d.id;
-- All students and departments combined

-- SELF JOIN
SELECT A.name, B.name FROM students A, students B WHERE A.id != B.id;
-- Pairs of students excluding self

-- CROSS JOIN
SELECT A.name, B.name FROM students A CROSS JOIN departments B;
-- Every student paired with every department
```

---

## 🟣 6. Functions

```sql
-- String Functions
SELECT CONCAT('Hello', ' ', 'World');
SELECT LENGTH('PostgreSQL');
SELECT SUBSTRING('PostgreSQL', 1, 4);

-- Numeric Functions
SELECT ROUND(5.678, 2);
SELECT CEIL(5.1);
SELECT FLOOR(5.9);

-- Date/Time Functions
SELECT NOW();
SELECT CURRENT_DATE;
SELECT AGE('2025-01-01', '2024-01-01');

-- Aggregate Functions
SELECT COUNT(*) FROM students;
SELECT AVG(age) FROM students;
SELECT MAX(age), MIN(age) FROM students;
```

---

## 🟠 7. Subqueries

```sql
-- Single row subquery
SELECT name FROM students WHERE age = (SELECT MAX(age) FROM students);

-- Multi-row subquery
SELECT name FROM students WHERE age IN (SELECT age FROM students WHERE age > 20);

-- Correlated subquery
SELECT name FROM students s WHERE age > (SELECT AVG(age) FROM students WHERE dept_id = s.dept_id);
```

---

## 🟡 8. Views

```sql
CREATE VIEW young_students AS SELECT * FROM students WHERE age < 21;
-- Creates a view

CREATE OR REPLACE VIEW young_students AS SELECT name FROM students WHERE age < 21;
-- Updates the view

DROP VIEW young_students;
-- Deletes the view
```

---

## 🟢 9. Indexes

```sql
CREATE INDEX idx_name ON students(name);
-- Creates an index on 'name'

CREATE INDEX idx_age_name ON students(age, name);
-- Composite index on age and name

DROP INDEX idx_name;
-- Removes the index
```

---

## 🔵 10. Stored Procedures & Functions

```sql
CREATE OR REPLACE FUNCTION get_all_students()
RETURNS TABLE(id INT, name VARCHAR, age INT, admission_date DATE) AS $$
BEGIN
  RETURN QUERY SELECT * FROM students;
END;
$$ LANGUAGE plpgsql;

SELECT * FROM get_all_students();
-- Calls the function
```

---

## 🟣 11. Triggers

```sql
CREATE OR REPLACE FUNCTION set_admission_date()
RETURNS TRIGGER AS $$
BEGIN
  NEW.admission_date := CURRENT_DATE;
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER before_insert_student
BEFORE INSERT ON students
FOR EACH ROW EXECUTE FUNCTION set_admission_date();
-- Sets admission_date automatically before insert
```

---

## 🟠 12. Transactions & ACID

```sql
BEGIN;
UPDATE students SET age = age + 1 WHERE age < 25;
COMMIT;
-- Commits changes

ROLLBACK;
-- Reverts changes if something goes wrong

SAVEPOINT sp1;
-- Creates a savepoint to rollback partially
```

---

## 🟡 13. User Management & Security

```sql
CREATE USER newuser WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE college TO newuser;
-- Creates a user and grants full access to 'college'

REVOKE ALL PRIVILEGES ON DATABASE college FROM newuser;
-- Revokes privileges
```

---

## 🟢 14. Backup and Restore

```bash
pg_dump -U postgres -F c -d college -f college_backup.dump
-- Backups database in custom format

pg_restore -U postgres -d college college_backup.dump
-- Restores database from backup
```

---

## 🔵 15. Performance Tuning & Optimization

```sql
EXPLAIN ANALYZE SELECT * FROM students WHERE age > 18;
-- Shows query execution plan and actual run time
```

---

## 🟣 16. PostgreSQL with Programming Languages

(No SQL queries — connection syntax varies by language: Python, Java, Node.js, etc.)

---

## 🟠 17. Tools and Clients

(Visual tools like pgAdmin, DBeaver, psql shell, no SQL queries needed)

---

## 🟡 18. Advanced Concepts

```sql
-- Partitioning Example
CREATE TABLE logs (
  id SERIAL,
  log_date DATE
) PARTITION BY RANGE (log_date);

CREATE TABLE logs_2024 PARTITION OF logs
FOR VALUES FROM ('2024-01-01') TO ('2025-01-01');

-- Logical Replication Setup
-- On Primary:
CREATE PUBLICATION mypub FOR TABLE students;

-- On Replica:
CREATE SUBSCRIPTION mysub CONNECTION 'host=primary_host dbname=college user=replicator password=secret' PUBLICATION mypub;
```

