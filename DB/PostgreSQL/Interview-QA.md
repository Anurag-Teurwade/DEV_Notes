
# 📘 PostgreSQL Interview Questions & Answers
---
## 🔹 Basic Questions (1-25)

### 1. What is PostgreSQL?
PostgreSQL is a free, open-source, object-relational database management system (ORDBMS) known for its reliability, feature robustness, and performance.

### 2. What is the difference between PostgreSQL and MySQL?
| Feature        | PostgreSQL          | MySQL               |
|---------------|--------------------|--------------------|
| License       | Open-source        | Open-source        |
| SQL Compliance| Highly compliant   | Partial compliance |
| ACID Support  | Full ACID          | Depends on storage engine |
| Performance   | Better for complex queries | Faster for simple reads |

### 3. How to create a database in PostgreSQL?
```sql
CREATE DATABASE myDatabase;
```

### 4. How do you delete a database?
```sql
DROP DATABASE myDatabase;
```

### 5. What is a schema in PostgreSQL?
A schema is a namespace that contains named database objects like tables, views, indexes, etc. It's like a folder in a filesystem.

### 6. How do you create a table?
```sql
CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(100) UNIQUE
);
```

### 7. What is SERIAL in PostgreSQL?
SERIAL is an auto-incrementing integer column type that automatically generates sequential numbers:
```sql
CREATE TABLE example (
  id SERIAL PRIMARY KEY
);
```

### 8. What is the default port of PostgreSQL?
The default port is **5432**.

### 9. What is a primary key?
A primary key is a column or set of columns that uniquely identifies each row in a table. It must contain unique values and cannot contain NULLs.

### 10. What are common data types in PostgreSQL?
- Integer: `SMALLINT`, `INTEGER`, `BIGINT`
- Decimal: `NUMERIC`, `DECIMAL`, `REAL`, `DOUBLE PRECISION`
- Text: `CHAR(n)`, `VARCHAR(n)`, `TEXT`
- Boolean: `BOOLEAN`
- Date/Time: `DATE`, `TIME`, `TIMESTAMP`, `INTERVAL`
- Special: `JSON`, `JSONB`, `ARRAY`, `UUID`

### 11. How to insert data into a table?
```sql
INSERT INTO students (name, email) 
VALUES ('John Doe', 'john@example.com');
```

### 12. How to update data?
```sql
UPDATE students 
SET email = 'newemail@example.com' 
WHERE id = 1;
```

### 13. How to delete data?
```sql
DELETE FROM students 
WHERE id = 1;
```

### 14. What is the difference between WHERE and HAVING?
- `WHERE` filters rows before grouping
- `HAVING` filters groups after the `GROUP BY` clause

### 15. What is a JOIN?
A JOIN combines rows from two or more tables based on related columns:
```sql
SELECT * FROM orders
JOIN customers ON orders.customer_id = customers.id;
```

### 16. What types of JOINs are supported?
- `INNER JOIN`: Returns matching rows
- `LEFT JOIN`: All left table rows + matching right rows
- `RIGHT JOIN`: All right table rows + matching left rows
- `FULL OUTER JOIN`: All rows when there's a match in either table
- `CROSS JOIN`: Cartesian product of all rows

### 17. What is a transaction?
A transaction is a sequence of operations performed as a single logical unit of work:
```sql
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

### 18. What are ACID properties?
- **Atomicity**: All operations succeed or none do
- **Consistency**: Database remains in consistent state
- **Isolation**: Concurrent transactions don't interfere
- **Durability**: Committed transactions survive crashes

### 19. What is indexing?
Indexes are special lookup tables that speed up data retrieval:
```sql
CREATE INDEX idx_student_name ON students(name);
```

### 20. What is a UNIQUE constraint?
Ensures all values in a column are different:
```sql
CREATE TABLE users (
  email VARCHAR(255) UNIQUE
);
```

### 21. What is a FOREIGN KEY?
A field that references the PRIMARY KEY in another table:
```sql
CREATE TABLE orders (
  id SERIAL PRIMARY KEY,
  customer_id INTEGER REFERENCES customers(id)
);
```

### 22. How to get the current date/time?
```sql
SELECT CURRENT_DATE;  -- Date only
SELECT CURRENT_TIME;  -- Time only
SELECT NOW();        -- Date and time with timezone
```

### 23. What is a sequence in PostgreSQL?
A database object that generates unique numbers:
```sql
CREATE SEQUENCE student_id_seq;
SELECT nextval('student_id_seq');
```

### 24. What is a VIEW?
A virtual table based on a SQL query:
```sql
CREATE VIEW active_users AS
SELECT * FROM users WHERE is_active = true;
```

### 25. How to list all databases?
```sql
\l  -- In psql
SELECT datname FROM pg_database;  -- SQL command
```

## 🔹 Advanced Questions (26-50)

### 26. Difference between TRUNCATE and DELETE?
| Feature       | TRUNCATE           | DELETE             |
|--------------|--------------------|--------------------|
| Speed        | Faster             | Slower             |
| WHERE clause | Not allowed        | Allowed            |
| Rollback     | Not always possible| Always possible    |
| Triggers     | Not fired          | Fired              |

### 27. Difference between CHAR and VARCHAR?
| Feature     | CHAR(n)            | VARCHAR(n)         |
|------------|--------------------|--------------------|
| Storage    | Fixed-length       | Variable-length    |
| Padding    | Pads with spaces   | No padding         |
| Usage      | When all values same length | When lengths vary |

### 28. What is a composite primary key?
A primary key made of multiple columns:
```sql
CREATE TABLE enrollments (
  student_id INT,
  course_id INT,
  PRIMARY KEY (student_id, course_id)
);
```

### 29. What is a subquery?
A query nested inside another query:
```sql
SELECT name FROM students 
WHERE id IN (SELECT student_id FROM enrollments);
```

### 30. How to rename a column?
```sql
ALTER TABLE students 
RENAME COLUMN name TO full_name;
```

### 31. What is a stored procedure?
A reusable database function:
```sql
CREATE OR REPLACE FUNCTION get_student_count()
RETURNS INTEGER AS $$
BEGIN
  RETURN (SELECT COUNT(*) FROM students);
END;
$$ LANGUAGE plpgsql;
```

### 32. What is a trigger?
A function that automatically executes when specified events occur:
```sql
CREATE TRIGGER update_timestamp
BEFORE UPDATE ON students
FOR EACH ROW EXECUTE FUNCTION update_modified_column();
```

### 33. Difference between ROW and RECORD?
- `ROW`: Predefined structure (specific columns)
- `RECORD`: Generic variable that can hold any row type

### 34. What is JSON support in PostgreSQL?
PostgreSQL has excellent JSON support with operators and functions:
```sql
SELECT info->>'name' FROM users WHERE info @> '{"active": true}';
```

### 35. What are arrays in PostgreSQL?
Columns can store arrays of any data type:
```sql
CREATE TABLE products (
  tags TEXT[]
);
INSERT INTO products VALUES (ARRAY['sale', 'electronics']);
```

### 36. What is the use of EXPLAIN?
Analyzes query execution plan:
```sql
EXPLAIN ANALYZE SELECT * FROM large_table;
```

### 37. How to add a column?
```sql
ALTER TABLE students 
ADD COLUMN age INTEGER;
```

### 38. How to remove a column?
```sql
ALTER TABLE students 
DROP COLUMN age;
```

### 39. Difference between UNION and UNION ALL?
- `UNION`: Removes duplicates
- `UNION ALL`: Keeps all rows (faster)

### 40. Difference between LIMIT and OFFSET?
- `LIMIT`: Restricts number of rows returned
- `OFFSET`: Skips specified number of rows
```sql
SELECT * FROM users LIMIT 10 OFFSET 20;  -- Rows 21-30
```

### 41. What is a cursor?
A pointer to a result set for row-by-row processing:
```sql
BEGIN;
DECLARE student_cursor CURSOR FOR SELECT * FROM students;
FETCH 10 FROM student_cursor;
CLOSE student_cursor;
COMMIT;
```

### 42. How to check PostgreSQL version?
```sql
SELECT version();
-- Or in psql:
\conninfo
```

### 43. What is MVCC?
Multi-Version Concurrency Control allows:
- Readers don't block writers
- Writers don't block readers
- Provides transaction isolation

### 44. What is a foreign data wrapper?
Allows querying external data sources:
```sql
CREATE EXTENSION postgres_fdw;
CREATE SERVER remote_server FOREIGN DATA WRAPPER postgres_fdw;
```

### 45. Difference between SERIAL and BIGSERIAL?
| Type      | Storage | Range              |
|----------|---------|--------------------|
| SERIAL   | 4 bytes | 1 to 2,147,483,647 |
| BIGSERIAL| 8 bytes | Much larger range   |

### 46. What is a tablespace?
A location where database objects are stored:
```sql
CREATE TABLESPACE fastspace LOCATION '/ssd/postgresql/data';
```

### 47. How to grant privileges?
```sql
GRANT SELECT, INSERT ON students TO analyst;
```

### 48. How to revoke privileges?
```sql
REVOKE INSERT ON students FROM analyst;
```

### 49. Difference between DELETE and DROP?
| Command | Effect                          |
|---------|---------------------------------|
| DELETE  | Removes rows from a table       |
| DROP    | Removes entire database objects |

### 50. What is WAL (Write-Ahead Logging)?
A method for ensuring data integrity:
- Changes are logged before being applied
- Enables crash recovery
- Supports replication
