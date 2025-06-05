
# MongoDB Commands :

---

## 1. Database & Collection Management

- **Show all databases:**

  ```js
  show dbs

* **Switch to a database / create if not exists:**

  ```js
  use myDatabase
  ```

* **Drop a database:**

  ```js
  db.dropDatabase()
  ```

* **Show all collections:**

  ```js
  show collections
  ```

* **Create collection:**

  ```js
  db.createCollection("myCollection")
  ```

* **Drop collection:**

  ```js
  db.myCollection.drop()
  ```

* **Rename collection:**

  ```js
  db.myCollection.renameCollection("newCollectionName")
  ```

---

## 2. CRUD Operations

### Insert

* Insert one document:

  ```js
  db.myCollection.insertOne({ name: "Alice", age: 25 })
  ```

* Insert many documents:

  ```js
  db.myCollection.insertMany([{ name: "Bob" }, { name: "Carol" }])
  ```

* Insert with options:

  ```js
  db.myCollection.insertOne({ name: "Dave" }, { bypassDocumentValidation: true })
  ```

### Find

* Find all documents:

  ```js
  db.myCollection.find()
  ```

* Find with filter:

  ```js
  db.myCollection.find({ age: { $gt: 20 } })
  ```

* Find one document:

  ```js
  db.myCollection.findOne({ name: "Alice" })
  ```

* Find with projection:

  ```js
  db.myCollection.find({}, { name: 1, _id: 0 })
  ```

* Find with limit and skip:

  ```js
  db.myCollection.find().limit(5).skip(10)
  ```

* Count documents matching filter:

  ```js
  db.myCollection.countDocuments({ age: { $gte: 18 } })
  ```

### Update

* Update one document:

  ```js
  db.myCollection.updateOne({ name: "Alice" }, { $set: { age: 26 } })
  ```

* Update many documents:

  ```js
  db.myCollection.updateMany({ age: { $lt: 30 } }, { $inc: { age: 1 } })
  ```

* Replace one document:

  ```js
  db.myCollection.replaceOne({ name: "Alice" }, { name: "Alice", age: 27 })
  ```

* Upsert document:

  ```js
  db.myCollection.updateOne({ name: "Eve" }, { $set: { age: 22 } }, { upsert: true })
  ```

### Delete

* Delete one document:

  ```js
  db.myCollection.deleteOne({ name: "Bob" })
  ```

* Delete many documents:

  ```js
  db.myCollection.deleteMany({ age: { $lt: 25 } })
  ```

* Remove all documents:

  ```js
  db.myCollection.deleteMany({})
  ```

---

## 3. Query Operators

* Comparison: `$eq`, `$ne`, `$gt`, `$gte`, `$lt`, `$lte`, `$in`, `$nin`
* Logical: `$and`, `$or`, `$not`, `$nor`
* Element: `$exists`, `$type`
* Evaluation: `$regex`, `$expr`, `$mod`
* Array: `$all`, `$elemMatch`, `$size`, `$slice`

---

## 4. Indexing

* Create ascending index:

  ```js
  db.myCollection.createIndex({ name: 1 })
  ```

* Create descending index:

  ```js
  db.myCollection.createIndex({ age: -1 })
  ```

* Create compound index:

  ```js
  db.myCollection.createIndex({ name: 1, age: -1 })
  ```

* Create unique index:

  ```js
  db.myCollection.createIndex({ email: 1 }, { unique: true })
  ```

* TTL index (expire documents):

  ```js
  db.myCollection.createIndex({ createdAt: 1 }, { expireAfterSeconds: 3600 })
  ```

* Text index:

  ```js
  db.myCollection.createIndex({ description: "text" })
  ```

* Drop index by name:

  ```js
  db.myCollection.dropIndex("name_1")
  ```

* List indexes:

  ```js
  db.myCollection.getIndexes()
  ```

---

## 5. Aggregation Framework

* Basic pipeline:

  ```js
  db.myCollection.aggregate([
    { $match: { status: "A" } },
    { $group: { _id: "$cust_id", total: { $sum: "$amount" } } },
    { $sort: { total: -1 } }
  ])
  ```

* Common stages:

  * `$match`
  * `$group`
  * `$project`
  * `$sort`
  * `$limit`
  * `$skip`
  * `$unwind`
  * `$lookup`
  * `$facet`
  * `$bucket`, `$bucketAuto`

* Lookup (join):

  ```js
  db.orders.aggregate([
    {
      $lookup: {
        from: "products",
        localField: "product_id",
        foreignField: "_id",
        as: "productDetails"
      }
    }
  ])
  ```

---

## 6. Transactions (Multi-Document ACID)

* Start session & transaction:

  ```js
  const session = client.startSession();
  session.startTransaction();
  ```

* Commit transaction:

  ```js
  await session.commitTransaction();
  session.endSession();
  ```

* Abort transaction:

  ```js
  await session.abortTransaction();
  session.endSession();
  ```

* Example with try/catch:

  ```js
  try {
    session.startTransaction();
    await collection1.insertOne(doc1, { session });
    await collection2.updateOne(filter, update, { session });
    await session.commitTransaction();
  } catch (error) {
    await session.abortTransaction();
  } finally {
    session.endSession();
  }
  ```

---

## 7. Replication & Sharding

* Initiate replica set:

  ```js
  rs.initiate()
  ```

* Check replica set status:

  ```js
  rs.status()
  ```

* Add member:

  ```js
  rs.add("mongodb2.example.net:27017")
  ```

* Remove member:

  ```js
  rs.remove("mongodb3.example.net:27017")
  ```

* Enable sharding:

  ```js
  sh.enableSharding("myDatabase")
  ```

* Shard collection:

  ```js
  sh.shardCollection("myDatabase.myCollection", { userId: 1 })
  ```

* Show shards:

  ```js
  sh.status()
  ```

---

## 8. User & Role Management

* Create user:

  ```js
  db.createUser({
    user: "appUser",
    pwd: "password123",
    roles: [{ role: "readWrite", db: "myDatabase" }]
  })
  ```

* Update password:

  ```js
  db.updateUser("appUser", { pwd: "newPassword" })
  ```

* Grant roles:

  ```js
  db.grantRolesToUser("appUser", [{ role: "dbAdmin", db: "myDatabase" }])
  ```

* Revoke roles:

  ```js
  db.revokeRolesFromUser("appUser", [{ role: "readWrite", db: "myDatabase" }])
  ```

* Drop user:

  ```js
  db.dropUser("appUser")
  ```

* Show users:

  ```js
  show users
  ```

---

## 9. Backup & Restore

* Backup database:

  ```bash
  mongodump --db myDatabase --out /backup/location
  ```

* Backup entire server:

  ```bash
  mongodump --out /backup/location
  ```

* Restore database:

  ```bash
  mongorestore --db myDatabase /backup/location/myDatabase
  ```

* Restore entire dump:

  ```bash
  mongorestore /backup/location
  ```

---

## 10. Monitoring & Maintenance

* Show current operations:

  ```js
  db.currentOp()
  ```

* Kill operation:

  ```js
  db.killOp(opid)
  ```

* Server status:

  ```js
  db.serverStatus()
  ```

* Database stats:

  ```js
  db.stats()
  ```

* Collection stats:

  ```js
  db.myCollection.stats()
  ```

* Compact collection:

  ```js
  db.myCollection.compact()
  ```

* Repair database (shell command):

  ```bash
  mongod --repair
  ```

* Flush logs:

  ```js
  db.adminCommand({ logRotate: 1 })
  ```

---

## 11. Miscellaneous

* Get current database:

  ```js
  db
  ```

* Show version/build info:

  ```js
  db.version()
  db.serverBuildInfo()
  ```

* Ping server:

  ```js
  db.adminCommand({ ping: 1 })
  ```

* List all roles:

  ```js
  db.getRoles({ showBuiltinRoles: true })
  ```

* Validate collection:

  ```js
  db.myCollection.validate({ full: true })
  ```

* Enable profiling:

  ```js
  db.setProfilingLevel(2)
  ```

* View profiling data:

  ```js
  db.system.profile.find().pretty()
  ```


