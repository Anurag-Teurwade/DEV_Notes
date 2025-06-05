# MongoDB Interview Questions & Answers


### 1. What is MongoDB?  
**Answer:** MongoDB is a NoSQL document-oriented database that stores data in flexible, JSON-like documents.

### 2. What is a document in MongoDB?  
**Answer:** A document is a record in MongoDB, stored in BSON format, similar to JSON.

### 3. What is a collection?  
**Answer:** A collection is a group of MongoDB documents, similar to a table in relational databases.

### 4. What is BSON?  
**Answer:** BSON (Binary JSON) is a binary-encoded serialization of JSON-like documents used in MongoDB.

### 5. How is MongoDB different from an RDBMS?  
**Answer:** MongoDB is schema-less, stores data as documents, and scales horizontally, unlike RDBMS which is table-based and uses fixed schema.

### 6. What is the use of the `_id` field?  
**Answer:** `_id` is a unique identifier automatically created for each document.

### 7. How do you insert a document in MongoDB?  
**Answer:** Using `insertOne()` or `insertMany()` methods.

### 8. How do you query documents in MongoDB?  
**Answer:** Using the `find()` method.

### 9. What are indexes?  
**Answer:** Indexes improve query performance by allowing fast data retrieval.

### 10. What types of indexes does MongoDB support?  
**Answer:** Single field, compound, unique, TTL, geospatial, text indexes.

### 11. What is a replica set?  
**Answer:** A group of MongoDB servers maintaining the same data set for high availability.

### 12. What is sharding?  
**Answer:** Sharding is horizontal scaling by distributing data across multiple servers.

### 13. What is the aggregation framework?  
**Answer:** A pipeline for processing and transforming documents to return computed results.

### 14. What is the difference between `updateOne()` and `replaceOne()`?  
**Answer:** `updateOne()` updates specified fields, `replaceOne()` replaces the entire document.

### 15. What is a capped collection?  
**Answer:** A fixed-size collection that overwrites oldest documents when it reaches its size limit.

### 16. How do you perform a text search in MongoDB?  
**Answer:** By creating a text index and using `$text` query operator.

### 17. What is the purpose of the `$lookup` stage?  
**Answer:** To perform a left outer join with another collection.

### 18. What are the types of relationships in MongoDB?  
**Answer:** Embedding (denormalization) and referencing (normalization).

### 19. How can you secure MongoDB?  
**Answer:** Using authentication, authorization (RBAC), encryption, and network security.

### 20. What is a transaction in MongoDB?  
**Answer:** An operation that ensures multiple updates succeed or fail as one atomic unit.

### 21. How do you backup MongoDB data?  
**Answer:** Using `mongodump` and `mongorestore` tools or cloud backups via Atlas.

### 22. What is the purpose of the `explain()` method?  
**Answer:** To analyze query execution plans for optimization.

### 23. What is the default storage engine for MongoDB?  
**Answer:** WiredTiger.

### 24. What is MongoDB Atlas?  
**Answer:** A fully managed cloud MongoDB service.

### 25. How is schema designed in MongoDB?  
**Answer:** Based on application needs, using embedded documents or references.

### 26. What is a TTL index?  
**Answer:** Time To Live index that automatically deletes documents after a set time.

### 27. How do you update multiple documents?  
**Answer:** Using `updateMany()`.

### 28. What data types does MongoDB support?  
**Answer:** String, Number, Boolean, Array, ObjectId, Date, Null, etc.

### 29. What is an ObjectId?  
**Answer:** A 12-byte unique identifier for documents in MongoDB.

### 30. Can MongoDB handle transactions across multiple documents?  
**Answer:** Yes, MongoDB supports multi-document ACID transactions.

### 31. What is the use of the aggregation `$group` stage?  
**Answer:** To group documents by a specified key and perform aggregations like sum or average.

### 32. How do you delete a document?  
**Answer:** Using `deleteOne()` or `deleteMany()`.

### 33. What is the use of the `$match` stage in aggregation?  
**Answer:** Filters documents based on specified criteria.

### 34. How does MongoDB handle scaling?  
**Answer:** Via sharding and replica sets.

### 35. What is a compound index?  
**Answer:** An index on multiple fields.

### 36. What is the difference between MongoDB and CouchDB?  
**Answer:** MongoDB uses BSON and supports rich querying; CouchDB uses JSON and focuses on replication.

### 37. How do you perform pagination in MongoDB?  
**Answer:** Using `.skip()` and `.limit()` methods.

### 38. What is GridFS?  
**Answer:** A specification for storing and retrieving large files in MongoDB.

### 39. What is the aggregation `$project` stage?  
**Answer:** Reshapes documents by including, excluding, or adding fields.

### 40. What is a session in MongoDB?  
**Answer:** A context to group operations for transactions.

### 41. What tools are available for monitoring MongoDB?  
**Answer:** MongoDB Cloud Manager, Ops Manager, Atlas monitoring.

### 42. How do you create a new user in MongoDB?  
**Answer:** Using `db.createUser()` with roles and privileges.

### 43. What is role-based access control (RBAC)?  
**Answer:** A method to restrict database access based on user roles.

### 44. How is data encrypted in MongoDB?  
**Answer:** Encryption at rest and in transit using TLS/SSL.

### 45. How do you import data into MongoDB?  
**Answer:** Using `mongoimport` tool.

### 46. What is the difference between `findOne()` and `find()`?  
**Answer:** `findOne()` returns a single document, `find()` returns a cursor for multiple documents.

### 47. How can you optimize query performance?  
**Answer:** By creating proper indexes and analyzing with `explain()`.

### 48. What is a projection in MongoDB queries?  
**Answer:** Selecting which fields to include or exclude in results.

### 49. How do you connect MongoDB to Node.js?  
**Answer:** Using the official MongoDB Node.js driver or ODM like Mongoose.

### 50. What is the difference between embedded documents and references?  
**Answer:** Embedded documents store related data within the same document; references store the related document's ID.


