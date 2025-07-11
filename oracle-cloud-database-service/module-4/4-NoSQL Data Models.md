# 🧩 Oracle NoSQL Database Cloud Service: Data Models

Welcome to the lesson on **Oracle NoSQL Database Cloud Service – Data Models**.  
In this session, we’ll explore the structure of NoSQL tables, supported data types, permissions, connectivity, and indexing capabilities.

---

## 🧱 NoSQL Table Anatomy

Every NoSQL table has two main components:

### 1️⃣ Data Component

- **Table Definition** with support for various data types:
  - `Integer`, `String`, `Binary`, `Long`, `Double`, `JSON`, `Record`, and more
- **Example**:  
  A table with:
  - `ID` (Primary Key): Integer  
  - `Name`: String  
  - `Type`: String  
  - `Details`: JSON

- **Shard Keys**:
  - Used to distribute data efficiently across shards
  - Records with the same shard key are stored closely together for faster access

---

### 2️⃣ Capacity Component

Defines resource limits for table operations:

| Type       | Unit          | Description                                 |
|------------|---------------|---------------------------------------------|
| 📦 Storage | Gigabytes     | Max data stored in the table                |
| 🧮 Throughput | Write Units / Read Units | Number of operations per second       |

---

## 🧪 Supported Data Types

Oracle NoSQL supports a **wide range of data types** for flexibility and rich data modeling.

✅ JSON, ✅ Records, ✅ Arrays  
✅ Maps, ✅ Booleans, ✅ Numbers, ✅ Timestamps, and more

---

## 🔑 Service Connectivity

To connect to Oracle NoSQL Cloud, you'll need:

- 🔐 **Tenancy OCID**
- 👤 **User OCID**
- 🧾 **API Signing Key & Fingerprint**
- 🧩 *(Optional)* Passphrase for extra security

---

## 🗃️ NoSQL Resources & Permissions

### 🎯 Resources
- **Tables**
- **Rows**
- **Indexes**

### 🔒 Permissions
Each resource has its own set of permissions for access control:

| Resource | Common Permissions |
|----------|---------------------|
| 🗂️ Tables   | Inspect, Read, Alter, Create, Move |
| 📄 Rows     | Read, Insert, Delete, Upsert        |
| 🧾 Indexes  | Inspect, Create, Delete             |

These permissions apply to **REST APIs** and **Cloud Driver APIs**.

---

## 🔄 Schema Flexibility & Interoperability

Oracle NoSQL supports both:

- **📑 Fixed Schema**: Defined structure with typed columns
- **🧾 Schemaless**: JSON objects with dynamic fields

✅ Both models can interoperate  
✅ SQL queries use identical syntax for both  

**Example** Query:  
Find all male visitors aged 24–30 in November  
(Same SQL applies to fixed or schemaless schema)

---

## 🔍 Rich Secondary Indexing

- Index any structure:  
  ✅ Scalars, ✅ Non-scalars, ✅ Composite keys, ✅ JSON fields  
- Use **path expressions** to drill into JSON structures  
- Enables fast and flexible query performance

---

## 🧾 Summary

| Feature             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| 📂 Table Structure   | Flexible schema with primary keys and optional shard keys                   |
| 📏 Data Types        | Rich support including JSON, numbers, arrays, records, timestamps, and more |
| 🔐 Connectivity      | OCID-based auth with secure key-based access                                |
| 👥 Permissions       | Fine-grained access per table, row, or index                                |
| 🔄 Schema Support    | Full interoperability between fixed and schemaless schemas                  |
| 📈 Indexing          | Powerful secondary indexing with JSON path access                           |

---

## 🙌 Thanks for Joining!

This concludes our lesson on **Oracle NoSQL Database Cloud Service Data Models**.  
We hope you now feel confident in designing flexible and efficient data structures for your NoSQL applications!
