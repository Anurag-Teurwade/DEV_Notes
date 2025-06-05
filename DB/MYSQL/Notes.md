
# 🐬 MySQL Notes : 

## 🟢 1. Introduction to MySQL
### 🔹 What is MySQL?
MySQL is an open-source Relational Database Management System (RDBMS) that uses SQL (Structured Query Language) to manage and manipulate data.

### 🔹 Features and Advantages
- Open-source and free
- Cross-platform support
- Fast and reliable
- Large community support
- Supports large databases

### 🔹 MySQL vs Other RDBMS
| Feature         | MySQL        | PostgreSQL | Oracle     | SQL Server |
|----------------|--------------|------------|------------|------------|
| Open-source    | Yes          | Yes        | No         | No         |
| Speed          | Fast         | Medium     | High       | High       |
| ACID Compliance| Good         | Excellent  | Excellent  | Excellent  |

---

## 🔵 2. Installation & Configuration
- Installing on Windows, Linux, and Mac
- Using MySQL Workbench (GUI) and Command Line Interface (CLI)
- Connecting to MySQL server via terminal or Workbench

---

## 🟣 3. Database Basics
- **Database**: Collection of organized data
- **Table**: Structured format for storing data
- **Row**: Record
- **Column**: Field
- **Data Types**: `INT`, `VARCHAR`, `TEXT`, `DATE`, `DATETIME`, etc.
- Special Attributes:
  - `NULL`: Empty value
  - `DEFAULT`: Default column value
  - `AUTO_INCREMENT`: Automatically increases numeric value

---

## 🟠 4. CRUD Operations
- `CREATE DATABASE db_name;`
- `CREATE TABLE table_name (...);`
- `INSERT INTO table_name VALUES (...);`
- `SELECT * FROM table_name;`
- `UPDATE table_name SET column=value WHERE condition;`
- `DELETE FROM table_name WHERE condition;`

---

## 🟡 5. Constraints
- `NOT NULL`: No empty values
- `UNIQUE`: No duplicate values
- `PRIMARY KEY`: Unique + Not Null
- `FOREIGN KEY`: Link to another table
- `CHECK`: Custom condition
- `DEFAULT`: Default value if not provided

---

## 🟢 6. SQL Clauses
- `WHERE`: Filter records
- `ORDER BY`: Sort results
- `GROUP BY`: Group records
- `HAVING`: Conditions on groups
- `LIMIT`: Restrict number of rows
- `DISTINCT`: Remove duplicates
- `BETWEEN`, `IN`, `LIKE`: Match values

---

## 🔵 7. Joins
- **INNER JOIN**: Matches rows in both tables
- **LEFT JOIN**: All from left + matches from right
- **RIGHT JOIN**: All from right + matches from left
- **FULL OUTER JOIN**: Combines LEFT + RIGHT (via `UNION`)
- **SELF JOIN**: Join the same table
- **CROSS JOIN**: Cartesian product of rows

---

## 🟣 8. Functions
### 🔹 String Functions
- `CONCAT()`, `LENGTH()`, `SUBSTRING()`

### 🔹 Numeric Functions
- `ROUND()`, `CEIL()`, `FLOOR()`

### 🔹 Date Functions
- `NOW()`, `CURDATE()`, `DATEDIFF()`

### 🔹 Aggregate Functions
- `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`

---

## 🟠 9. Subqueries
- **Single-row vs Multi-row** subqueries
- **Correlated Subqueries**: Inner query depends on outer query
- Use in: `SELECT`, `WHERE`, `FROM`, `HAVING`

---

## 🟡 10. Views
- `CREATE VIEW view_name AS SELECT ...`
- `ALTER VIEW view_name AS SELECT ...`
- `DROP VIEW view_name;`
- Updatable views with certain restrictions

---

## 🟢 11. Indexes
- Speed up data retrieval
- **Single Index**: One column
- **Composite Index**: Multiple columns
- `CREATE INDEX`, `DROP INDEX`
- Indexing Strategy: Use for WHERE, JOIN, ORDER BY

---

## 🔵 12. Stored Procedures & Functions
- `CREATE PROCEDURE`, `CREATE FUNCTION`
- Parameters: `IN`, `OUT`, `INOUT`
- `CALL procedure_name(...)`
- Use `DELIMITER` to define blocks

---

## 🟣 13. Triggers
- Automatically run when INSERT, UPDATE, DELETE happens
- Types: `BEFORE`, `AFTER`
- Example:
  ```sql
  CREATE TRIGGER trg_before_insert
  BEFORE INSERT ON table_name
  FOR EACH ROW
  BEGIN
    -- statements
  END;

---

## 🟠 14. Transactions & ACID

* **ACID**: Atomicity, Consistency, Isolation, Durability
* `START TRANSACTION`, `COMMIT`, `ROLLBACK`
* `SAVEPOINT sp_name`, `ROLLBACK TO sp_name`
* Isolation levels: `READ COMMITTED`, `REPEATABLE READ`, etc.

---

## 🟡 15. User Management & Security

* Create User: `CREATE USER 'user'@'host' IDENTIFIED BY 'pass';`
* Grant Privileges: `GRANT SELECT, INSERT ON db.* TO 'user';`
* Revoke Privileges: `REVOKE SELECT ON db.* FROM 'user';`
* Apply changes: `FLUSH PRIVILEGES;`
* Use of Authentication Plugins (e.g., `mysql_native_password`)

---

## 🟢 16. Backup and Restore

* `mysqldump`: Backup tool (Logical)

  ```bash
  mysqldump -u root -p database_name > backup.sql
  ```
* `mysqlimport`: Import tool
* Import SQL:

  ```bash
  mysql -u root -p database_name < backup.sql
  ```

---

## 🔵 17. Performance Tuning & Optimization

* Use `EXPLAIN SELECT ...` to analyze query performance
* Proper indexing
* Avoid `SELECT *` in large datasets
* Use caching, connection pooling, query rewriting

---

## 🟣 18. MySQL with Programming Languages

### 🔹 PHP

* PDO, MySQLi

### 🔹 Python

* `mysql-connector-python` or `PyMySQL`

### 🔹 Java

* JDBC Driver for MySQL

---

## 🟠 19. MySQL Workbench

* Visual ER Model creation
* Forward Engineering: Design → DB
* Reverse Engineering: DB → Model
* Data modeling and schema management

---

## 🟡 20. Advanced Concepts

### 🔹 Partitioning

* Dividing a table into parts (RANGE, LIST, HASH)

### 🔹 Replication

* **Master-Slave**: One server writes, others read
* Use for high availability & load balancing

### 🔹 Sharding

* Splitting database horizontally across multiple machines

### 🔹 Event Scheduler

* Automate tasks at scheduled times

  ```sql
  CREATE EVENT ev_name
  ON SCHEDULE EVERY 1 DAY
  DO
    UPDATE table SET column = value;
  ```


