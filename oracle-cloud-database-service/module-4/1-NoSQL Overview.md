# ☁️ Oracle NoSQL Database Cloud Service Overview

👋 Hi, friends! Welcome to this Oracle University module presented by **Sara**.  
In this session, we’ll explore how Oracle NoSQL Database Cloud Service helps address modern application challenges with a powerful, scalable, and developer-friendly platform.

---

## 📚 What You'll Learn

We’ll cover:
1. Modern application challenges
2. Oracle NoSQL Database Cloud Service overview
3. Common use cases and features
4. Supported data models and security
5. Developer tools and deployment options

---

## ⚠️ Modern App Challenges

Modern applications demand:

- 💾 High-volume, high-speed data ingestion (e.g., IoT, logs)
- ⚡ Instant responsiveness (e.g., product recommendations)
- 🧠 Rapid innovation cycles and data model changes
- 🔄 Always-on availability and dynamic scaling
- 💸 Cost-effective operations with minimal infrastructure overhead

---

## 🚀 Introducing Oracle NoSQL Database Cloud Service

Oracle NoSQL Cloud is:

- **Serverless & fully managed**
- **Elastic**: auto-scales storage & throughput
- **Low latency** (< 10 ms)
- **Flexible data models**: Key-Value, Document (JSON), Columnar
- **Dev-friendly** APIs (Java, Python, Node.js, Go, Spring)
- **Secure**: Identity & Access Mgmt (IAM), Encryption at rest/in-motion
- **Multi/hybrid-cloud ready**

> Developers focus on **apps**, not infrastructure.

---

## 🧠 Common Use Cases

| Use Case            | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Social Media        | Store user-generated content (comments, chats, likes, etc.)                 |
| IoT                 | Ingest high-velocity sensor data for real-time analytics                    |
| Customer 360        | Unify customer data across platforms for personalized services              |
| Catalog Data        | Store metadata like user accounts, products, BOM, IoT registries            |
| Online Gaming       | Fast response for real-time gameplay, scores, and user state                |
| User Profiles       | Render personalized UI using live user data                                 |
| Other               | Content management, real-time analytics, anomaly detection, ad targeting    |

---

## 🌐 Global Availability & Deployment Flexibility

- ✅ Available in **22+ OCI regions**
- ☁️ Run **anywhere**: Oracle Cloud, other clouds, on-premise
- 🔀 Supports **hybrid deployments**

---

## 🗂️ Supported Data Models

Oracle NoSQL supports:

1. **Columnar (Relational Schema)**  
   - Predefined columns & datatypes
2. **Document (JSON)**  
   - Schemaless and flexible
3. **Key-Value**  
   - Simple mappings for fast access

➡️ All models **interoperate** using the same SQL & APIs.

---

## 🔒 Enterprise-Grade Security

- **IAM Integration**: Control user/group access to resources
- **Compartments**: Logical resource isolation for billing & governance
- **Policies**: SQL-like syntax for easy permission management
- **Encryption**: Data protected at rest and in motion

---

## 📊 Elastic Scaling & Cost Optimization

- ⚙️ Provision **read/write throughput** and **storage** as needed
- 📈 Scale up during high load (e.g., holiday sales)
- 📉 Scale down in low traffic periods
- 💰 Pay only for what you use — **no overprovisioning**

### 📅 Weekday Usage Example:

| Day      | Read/Write Load | Provisioned Throughput | Cost Impact         |
|----------|------------------|------------------------|---------------------|
| Monday   | Low              | Low                    | 💲 Low              |
| Wednesday| High             | High                   | 💲💲💲 High           |
| Friday   | Medium-High      | Adjusted as needed     | 💲💲 Medium-High     |

---

## 🏎️ Powered by Oracle Gen 2 Cloud Infrastructure

- ⚡ NVMe SSDs = **Millions of TPS**
- 🔒 No tenant oversubscription
- 🔁 High performance and consistent low latency
- 🧱 Leverages modern CPUs, GPUs, and enterprise-grade networking

---

## 👩‍💻 Developer Experience

- 🧩 **Drivers** for Java, Node.js, Python, Go, Spring Data, etc.
- 🛠️ Minimal setup — create NoSQL tables in seconds
- 🎯 Focus on **developing apps**, not managing infra
- 📦 Same app works on-prem, in cloud, or both (hybrid-ready)

---

Key Benefits
🚀 Accelerated Innovation: Businesses can focus on new features, not infrastructure.

⚙️ Managed by Oracle: No need for IT to handle updates, high availability, or resource management.

🔐 Admin Control: DBAs manage authentication and access privileges.

Table Essentials
Each table has two main parts: Data and Capacity.

Data Components
📝 Flexible Data Types: Supports integers, strings, JSON, and more.

🏗️ Schema Options: Use fixed schemas or work with schema-less data.

🔑 Smart Keys: Primary keys for access, shard keys for efficient data distribution.

Capacity Components
💾 Storage: Measured in gigabytes.

⚡ Throughput: Governs reads and writes (read units, write units).

🔄 Dynamic Scaling: Easily increase or decrease capacity as needed.

Data Consistency
Choose the right consistency for your needs:

⏳ Eventual Consistency: Faster reads (1 read unit), but might return older data.

✅ Absolute Consistency: Guarantees the latest data (2 read units).

Core Features
⏱️ Time to Live (TTL): Automatically ages data at table or record level.

💻 API & SQL Access: Interact with your data using powerful APIs and rich SQL, including JSON queries.

🔍 Advanced Indexing: Easily index various data types and JSON fields for fast searches.

Cost Model
💰 Hourly Billing: Pay only for what you provision.

💲 Unit-Based: Costs are based on read and write units, not underlying server resources.

Connectivity & Security
🔗 Simple Connection: Requires Oracle Cloud IDs (OCIDs) and API signing keys.

🔒 Granular Permissions: Control access to tables, rows, and indexes with specific permissions for different operations.

SQL Capabilities
The service offers a comprehensive SQL language with various functionalities:

Predicates & Projections:

Filtering (WHERE clause): Use WHERE clauses to filter data, including nested JSON fields and string functions (e.g., LIKE).

Sorting: Order your query results using ORDER BY.

Projections: Select specific fields, including scalar values or fragments of JSON documents, rather than the entire document.

Paging:

LIMIT Clause: Specifies the maximum number of results to return.

OFFSET Clause: Skips a specified number of initial query results, enabling efficient pagination for large datasets.

Group By & Aggregates:

Aggregate Functions: Perform calculations like MIN, MAX, AVG, SUM, and COUNT.

Time Extractions: Extract specific units (year, month, day, hour, minute) from timestamps.

GROUP BY: Group rows that have the same values in specified columns into a summary row.

Advanced Operations
Oracle NoSQL supports advanced data operations for complex use cases:

Data Modification:

INSERT: Add new rows.

UPSERT: Update existing rows or insert new ones if they don't exist.

Single SQL Statements: Perform multiple operations (set, add, remove, put) on arrays and maps within a single SQL query.

Shard Local Joins & Regular Expressions: Enhance query flexibility and performance for distributed data.

Nested Tables (Parent/Child Relationships):

Create joins between parent and child tables, allowing for deep, unlimited hierarchical data structures.

Project data from parent tables using ANCESTORS and from child tables using DESCENDANTS. Each nested table can be accessed independently.

GeoJSON Support:

Adheres to the standard GeoJSON RFC 7946 structure (points, lines, polygons).

Geospatial Functions: geo_intersect, geo_inside, geo_withindistance, geo_near, and geo_distance to analyze spatial relationships.

ID Generation:

Identity Columns: Automatically generate values with defined start points and increments.

Caching: Cache a specified number of generated values (e.g., 1,000 entries) for performance.

Recycling: Option to recycle values after reaching the maximum limit.

Development & Deployment Options
Access and interact with Oracle NoSQL Database Cloud Service through various environments:

IDE Plugins: Available for popular IDEs like Eclipse and IntelliJ.

Access Approaches:

UI Console Service: A web-based console for basic functionality like creating tables, inserting/updating/selecting rows, and basic queries. It's great for initial exploration and quick understanding without needing to download drivers.

SQL Capabilities
The service offers a comprehensive SQL language for data manipulation and querying.

Predicates & Projections:

🔎 Filtering: Use WHERE clauses for data filtering, including nested JSON.

📤 Projections: Select specific fields or JSON fragments.

⬆️⬇️ Sorting: Order your query results.

Paging:

📏 LIMIT Clause: Sets max results to return.

⏭️ OFFSET Clause: Skips initial query results for pagination.

Group By & Aggregates:

➕➖ Aggregate Functions: Perform MIN, MAX, AVG, SUM, COUNT.

⏰ Time Extractions: Extract year, month, day, etc., from timestamps.

🧮 GROUP BY: Group rows for summary.

Advanced Operations
Oracle NoSQL supports advanced data operations for complex use cases.

Data Modification:

➕ INSERT: Add new rows.

✏️ UPSERT: Update existing rows or insert new ones.

📜 Single SQL Statements: Combine multiple operations like set, add, remove, put on arrays and maps.

🔗 Shard Local Joins & Regular Expressions: Enhanced query flexibility.

🌳 Nested Tables (Parent/Child Relationships):

Create joins between parent and child tables for deep hierarchies.

Access data from parents (ANCESTORS) or children (DESCENDANTS) independently.

🗺️ GeoJSON Support:

Adheres to RFC 7946 (points, lines, polygons).

🌐 Geospatial Functions: Analyze spatial relationships (e.g., geo_intersect, geo_distance).

🆔 ID Generation:

Identity Columns: Auto-generate values with defined increments.

📦 Caching: Cache generated values for performance.

♻️ Recycling: Option to reuse values after limits.

Development & Deployment Options
Access and interact with Oracle NoSQL Database Cloud Service through various environments.

🔌 IDE Plugins: Available for Eclipse and IntelliJ.

Access Approaches:

🖥️ UI Console Service: Web-based for basic functionality and quick exploration.

☁️ Cloud Service (Production): Full functionality for development and deployment with your application and driver.

🧪 Local Standalone NoSQL Simulator: Free, single-process environment for local testing without cloud costs.

Monitoring & Throttling
📊 OCI Console Monitoring: Track table capacities and performance.

🛑 Throttling Detection: Identify if requests are being throttled due to insufficient provisioned capacity, indicating a need to adjust.

Oracle NoSQL Differentiators
Oracle NoSQL stands out with unique advantages.

✨ Seamless Multi-Model: Key-value, fixed schema, and schema-less data in one store, with full interoperability.

🛡️ Tunable ACID: Shard-local full ACID compliance and ACID-compliant parent/child table operations.

🔄 Adjustable Consistency: Choose between eventual and strong consistency.

💯 Fully Managed & Flexible:

Run as a managed cloud service in Oracle Cloud.

🔓 No Lock-in: Deploy on other cloud providers if desired.

➡️⬅️ Hybrid Approach: Seamlessly integrate on-premise applications with cloud components – a powerful differentiator.
Cloud Service (Production): The primary approach for full functionality, deployment, and development in a production environment. Your application compiles with the Oracle NoSQL driver.

Local Standalone Client-Server NoSQL Simulator: A free, single-process environment that simulates the cloud service. Ideal for local development and testing without incurring cloud costs.

Monitoring & Throttling
OCI Console Monitoring: Monitor table capacities (read units, write units, storage) at different time intervals.

Throttling Detection: The monitoring helps identify if your requests are being throttled (e.g., attempting 200 read units with only 100 allocated). Throttling indicates a need to adjust your provisioned capacities.

Oracle NoSQL Differentiators
Oracle NoSQL stands out with several unique advantages:

Seamless Multi-Model: Stores key-value, fixed schema, and schema-less data in a single data store, with full interoperability.

Tunable ACID: Offers shard-local full ACID compliance and fully ACID-compliant parent/child table operations.

Adjustable Consistency: Provides choices between eventual and strong consistency.

Fully Managed & Flexible:

Run as a fully managed cloud service in Oracle Cloud.

No Lock-in: Deploy on other cloud providers if desired.

Hybrid Approach: Seamlessly integrate on-premise applications with cloud components, a powerful differentiator from competitors.
