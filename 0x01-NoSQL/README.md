# Short Notes

Here are brief notes on each topic:

### What NoSQL Means
NoSQL (Not Only SQL) refers to a class of database management systems designed to handle unstructured or semi-structured data. Unlike traditional SQL databases, NoSQL databases are schema-less, allowing for flexibility in data storage and retrieval.

### Difference Between SQL and NoSQL
- **Data Structure**: SQL databases use a structured schema with tables, rows, and columns; NoSQL databases allow for various data models (document, key-value, column-family, graph).
- **Scalability**: SQL databases are vertically scalable (adding resources to a single server); NoSQL databases are horizontally scalable (adding more servers).
- **Transactions**: SQL databases support ACID properties for transactions; NoSQL databases often prioritize availability and partition tolerance over strict consistency.

### What is ACID
ACID stands for:
- **Atomicity**: Ensures that all operations within a transaction are completed successfully or none at all.
- **Consistency**: Ensures that a transaction brings the database from one valid state to another.
- **Isolation**: Ensures that transactions are executed in isolation from one another.
- **Durability**: Guarantees that once a transaction is committed, it will remain so even in the event of a system failure.

### What is Document Storage
Document storage is a type of NoSQL database that stores data in documents, typically in JSON or BSON format. Each document can have a different structure, allowing for a flexible schema. This type of storage is commonly used for applications that require high scalability and diverse data types.

### NoSQL Types
1. **Document Stores**: Store data in documents (e.g., MongoDB, CouchDB).
2. **Key-Value Stores**: Store data as key-value pairs (e.g., Redis, DynamoDB).
3. **Column-Family Stores**: Store data in columns rather than rows (e.g., Cassandra, HBase).
4. **Graph Databases**: Store data in nodes and edges, suitable for complex relationships (e.g., Neo4j, Amazon Neptune).

### Benefits of a NoSQL Database
- **Scalability**: Easily scales out by adding more servers.
- **Flexibility**: Schema-less design allows for rapid iteration and evolution of data models.
- **High Performance**: Optimized for large volumes of data and high-speed operations.
- **Variety of Data Models**: Supports various types of data, making it suitable for diverse applications.

### How to Query Information from a NoSQL Database
Querying in NoSQL databases varies by type. For example, in MongoDB, you use methods like `find()` to retrieve documents:
```javascript
db.collection.find({ field: value })
```
This retrieves all documents where the specified field matches the value.

### How to Insert/Update/Delete Information from a NoSQL Database
- **Insert**: Use methods like `insertOne()` or `insertMany()` in MongoDB:
  ```javascript
  db.collection.insertOne({ name: "Alice", age: 25 })
  ```
- **Update**: Use `updateOne()` or `updateMany()`:
  ```javascript
  db.collection.updateOne({ name: "Alice" }, { $set: { age: 26 } })
  ```
- **Delete**: Use `deleteOne()` or `deleteMany()`:
  ```javascript
  db.collection.deleteOne({ name: "Alice" })
  ```

### How to Use MongoDB
1. **Installation**: Install MongoDB on your system or use a cloud service like MongoDB Atlas.
2. **Start the Server**: Use the command `mongod` to start the database server.
3. **Connect to the Database**: Use `mongo` command to access the MongoDB shell.
4. **Create a Database**: Use `use database_name` to create or switch to a database.
5. **Perform CRUD Operations**: Use the appropriate commands to create, read, update, or delete data as shown above.

These notes provide a concise overview of key concepts related to NoSQL databases. Let me know if you need more details on any specific topic!
