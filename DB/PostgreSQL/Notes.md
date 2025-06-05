# 📚 PostgreSQL Notes : 

## 1. Introduction to PostgreSQL

**What is PostgreSQL?**  
PostgreSQL is a powerful, open-source object-relational database system known for its reliability, feature robustness, and standards compliance.

**Features and Advantages**  
- ACID compliant transactions  
- Supports advanced data types like JSON, XML  
- Extensible with custom functions, data types  
- Strong community and regular updates  

**Installation & Setup**  
Available for Windows, Linux, and Mac. Installation can be done via package managers or from the official site.  

**PostgreSQL Architecture Overview**  
Client-server model with processes handling connections, background workers, and data storage.  

**Using psql CLI and pgAdmin GUI**  
- `psql` is the command-line tool for queries and management  
- `pgAdmin` is a graphical interface for easier database handling

---

## 2. Basic Database Concepts

- **Databases, Schemas, Tables**: A database contains schemas; schemas contain tables which hold the actual data.  
- **Data Types in PostgreSQL**: Common types include INTEGER, VARCHAR, TEXT, BOOLEAN, DATE, TIMESTAMP, JSON, etc.  
- **Creating and Managing Databases and Tables**: Using `CREATE DATABASE`, `CREATE TABLE` commands.  
- **Basic CRUD Operations**:  
  - SELECT: Read data  
  - INSERT: Add data  
  - UPDATE: Modify data  
  - DELETE: Remove data

---

## 3. Data Modeling & Constraints

- **Primary Key**: Uniquely identifies each row in a table.  
- **Foreign Key**: Links rows between tables, enforcing referential integrity.  
- **Unique & NOT NULL**: Ensure values are unique and not empty.  
- **Check Constraints**: Validate data based on conditions.  
- **Default Values**: Provide default data when none is supplied.

---

## 4. Advanced Querying

- **Filtering**: Use WHERE, BETWEEN, IN, LIKE to narrow down data.  
- **Sorting**: ORDER BY sorts query results ascending or descending.  
- **Aggregation Functions**: COUNT, SUM, AVG, MIN, MAX summarize data.  
- **Grouping Data**: GROUP BY groups rows; HAVING filters groups.  
- **Joins**: INNER, LEFT, RIGHT, FULL join tables on related columns.  
- **Subqueries and Correlated Subqueries**: Nested queries for complex data retrieval.  
- **Common Table Expressions (CTEs)**: Named temporary result sets to organize queries, support recursion.

---

## 5. Indexing & Performance

- **What is an Index?** A data structure that speeds up data retrieval.  
- **Types of Indexes**: B-tree (default), Hash, GIN (for arrays, JSON), GiST (for geometric data).  
- **Creating and Managing Indexes**: Using `CREATE INDEX` and `DROP INDEX`.  
- **Explain Analyze**: Shows the execution plan and performance details of queries.  
- **Vacuum and Autovacuum**: Clean up dead tuples and maintain database health.

---

## 6. Transactions & Concurrency

- **ACID Properties**: Atomicity, Consistency, Isolation, Durability guarantee safe transactions.  
- **Transaction Control Commands**:  
  - `BEGIN` starts a transaction  
  - `COMMIT` saves changes  
  - `ROLLBACK` undoes changes  
  - `SAVEPOINT` allows partial rollbacks  
- **Isolation Levels**: Control how visible transaction changes are to others (Read Committed, Repeatable Read, Serializable).  
- **Locking Mechanisms**: Prevent data conflicts during concurrent operations.

---

## 7. Functions & Stored Procedures

- **Creating Functions**: Use PL/pgSQL to write reusable code blocks.  
- **Control Structures**: IF, LOOP, CASE to add logic inside functions.  
- **Triggers**: Automatic functions run on data changes (INSERT, UPDATE, DELETE).  
- **Built-in Functions and Operators**: Extensive library for string, numeric, date, and JSON operations.

---

## 8. Views & Materialized Views

- **Creating Views**: Virtual tables representing query results.  
- **Updatable Views**: Views you can modify which affect underlying tables.  
- **Materialized Views**: Physically stored query results for faster access, can be refreshed periodically.

---

## 9. Security & User Management

- **Roles and Permissions**: Control access with roles (users or groups).  
- **Authentication Methods**: Passwords, certificates, LDAP, etc.  
- **Granting and Revoking Privileges**: Fine-grained access control using `GRANT` and `REVOKE`.  
- **Row-Level Security**: Policies to restrict rows visible to different users.

---

## 10. Backup & Restore

- **pg_dump and pg_restore**: Tools to export and import database data.  
- **Logical vs Physical Backups**: Logical dumps vs binary file backups.  
- **Point-in-Time Recovery (PITR)**: Restore database state to a specific moment.

---

## 11. Extensions & Advanced Features

- **Popular Extensions**:  
  - PostGIS (geospatial data)  
  - pg_stat_statements (query statistics)  
- **Full-Text Search**: Powerful text search functionality.  
- **JSON and JSONB**: Store and query JSON data efficiently.  
- **Partitioning Tables**: Divide large tables for performance.  
- **Foreign Data Wrappers (FDW)**: Access external data sources like other databases.

---

## 12. Replication & High Availability

- **Streaming Replication**: Real-time data copying to standby servers.  
- **Logical Replication**: Replicate specific tables or data.  
- **Hot Standby and Failover**: Read-only standby server for load balancing and automatic failover.

---

## 13. Monitoring & Maintenance

- **pg_stat Views**: Monitor activity, connections, locks, and queries.  
- **Logs and Error Reporting**: Track errors and slow queries for troubleshooting.  
- **Routine Maintenance Commands**: VACUUM, ANALYZE to keep the database performant.  
- **Autovacuum Tuning**: Adjust autovacuum behavior for workload.


