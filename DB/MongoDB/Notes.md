# 📚 MongoDB Complete Notes

## 🟢 1. Introduction to MongoDB

- **❓ What is MongoDB?**  
  MongoDB is a popular NoSQL database that stores data in flexible, JSON-like documents instead of tables.

- **✨ Features and Advantages:**  
  - Schema-less design  
  - High scalability and performance  
  - Easy to work with hierarchical data  
  - Supports replication and sharding  

- **📄 Document-oriented NoSQL database:**  
  Data is stored as documents, which are similar to JSON objects.

- **⚖️ Use Cases and Comparison with RDBMS:**  
  MongoDB is great for handling large volumes of unstructured data, while RDBMS uses structured tables and relationships.

---

## 💻 2. Installation & Setup

- **⬇️ Installing MongoDB on Windows/Linux/Mac:**  
  Download MongoDB from the official site and follow platform-specific installation guides.

- **☁️ MongoDB Atlas (Cloud Service) Overview:**  
  Atlas is a fully-managed cloud database for MongoDB, easy to set up without local installation.

- **🖥️ Mongo Shell and MongoDB Compass GUI:**  
  - Mongo Shell: Command line tool to interact with MongoDB  
  - Compass: Visual GUI to view, query, and manage data  

---

## 📘 3. MongoDB Basics

- **📂 Databases, Collections, and Documents:**  
  - Database: Container for collections  
  - Collection: Group of documents (like tables)  
  - Document: A record (like a row) stored as BSON (binary JSON)

- **📦 BSON Data Format:**  
  Binary format for storing JSON-like documents efficiently.

- **🛠️ CRUD Operations:**  
  - Create: `insertOne()`, `insertMany()`  
  - Read: `find()`, `findOne()`  
  - Update: `updateOne()`, `updateMany()`  
  - Delete: `deleteOne()`, `deleteMany()`

---

## 🏗️ 4. Data Modeling

- **📐 Schema Design Principles:**  
  Plan how your documents will be structured for performance and flexibility.

- **🧩 Embedded Documents vs References:**  
  - Embed related data inside a document for fast reads  
  - Use references (like foreign keys) for normalized data  

- **🔢 Data Types:**  
  String, Number, Date, Array, ObjectId (unique ID), Boolean, etc.

- **🔍 Indexing Basics and Types:**  
  Indexes speed up query performance by allowing fast lookups.

---

## 🔎 5. Querying Documents

- **⚙️ Query Operators:**  
  - Comparison: `$eq`, `$gt`, `$lt` etc.  
  - Logical: `$and`, `$or`, `$not`  
  - Element: `$exists`, `$type`

- **📋 Projection and Sorting:**  
  - Projection: Select which fields to return  
  - Sorting: Order results by one or more fields

- **🔄 Aggregation Pipeline Basics:**  
  Process documents through multiple stages for advanced queries.

- **🔤 Text Search and Regex Queries:**  
  Search text within fields or use pattern matching.

---

## ⚡ 6. Indexes & Performance

- **📌 Single Field and Compound Indexes:**  
  Index on one or multiple fields to improve query speed.

- **⏳ TTL (Time To Live) Indexes:**  
  Automatically delete documents after a certain time.

- **🌍 Geospatial Indexes:**  
  Support queries based on location data.

- **📊 Explain Plan and Query Optimization:**  
  Use `.explain()` to analyze how queries run and optimize them.

---

## 📊 7. Aggregation Framework

- **🧱 Pipeline Stages:**  
  - `$match`: Filter documents  
  - `$group`: Group documents by a key  
  - `$project`: Reshape documents  
  - `$sort`: Sort results  
  - `$lookup`: Join data from another collection

- **📈 Using Aggregations for Data Analysis:**  
  Aggregate data like sum, average, counts, etc.

---

## 🔄 8. Replication & Sharding

- **🛡️ Replica Sets for High Availability:**  
  Multiple copies of data for fault tolerance.

- **⚖️ Sharding for Horizontal Scaling:**  
  Split data across multiple servers to handle large datasets.

- **🔧 Setup and Management Basics:**  
  How to configure replica sets and shards.

---

## 🔐 9. Transactions

- **🔗 Multi-document ACID Transactions:**  
  Ensure multiple operations succeed or fail together.

- **🗂️ Session Management:**  
  Manage transaction sessions.

- **📋 Use Cases and Limitations:**  
  Useful when multiple documents need atomic updates; may impact performance.

---

## 🔒 10. Security & User Management

- **🔑 Authentication Methods:**  
  Username/password, LDAP, Kerberos, etc.

- **👥 Role-Based Access Control (RBAC):**  
  Assign roles with specific permissions.

- **🛡️ Encryption at Rest and in Transit:**  
  Secure data stored on disk and during network transfer.

---

## 💾 11. Backup & Restore

- **📦 mongodump and mongorestore:**  
  Command-line tools to backup and restore data.

- **☁️ Cloud Backups (Atlas Backups):**  
  Automated backups managed by MongoDB Atlas.

---

## 📈 12. Monitoring & Maintenance

- **📊 Monitoring Tools and Metrics:**  
  Track server health, operations, and performance.

- **📝 Logs and Performance Tuning:**  
  Analyze logs to find bottlenecks and tune settings.

- **🔄 Handling Data Migrations and Upgrades:**  
  Best practices for upgrading MongoDB versions safely.

---

## 🖥️ 13. MongoDB with Programming Languages

- **🔌 Drivers Overview:**  
  Official MongoDB drivers available for Node.js, Python, Java, C#, and more.

- **⚙️ Connecting and Basic Operations via Code:**  
  How to connect to MongoDB and perform CRUD operations from your application.


