# 🕸️ Creating, Querying, Analyzing & Visualizing Graphs in Oracle Autonomous Database

**Instructor:** Michelle
**Lesson Focus:** How to work with graph data in Oracle Autonomous Database — from building to visualizing it using SQL-like tools and automated features.

---

## 🏗️ Creating a Graph

You can model graphs from existing relational data like:

| Table        | Graph Representation  |
| ------------ | --------------------- |
| Accounts     | Vertices (nodes)      |
| Transactions | Edges (relationships) |

### 🔧 How to Create:

* Use **Property Graph DDL** to declare vertices and edges manually
* OR use **Automated Graph Modeling** in Autonomous Database:

  * Just select tables
  * Modeler infers relationships (e.g., via foreign keys)
  * You can customize the generated model

✅ **No complex setup needed!**

---

## 🔍 Querying a Graph

Graph queries are all about finding **patterns** in the graph.

### 💬 Syntax:

**Property Graph Query Language (PGQL)** — SQL-like with support for **graph patterns**.

#### 🧱 Graph Pattern Syntax:

* `(a)` → vertex
* `[e]` → edge
* `(a)-[e]->(b)` → edge from vertex a to b

### 🧪 Example Patterns:

| Pattern                             | Meaning                                    |
| ----------------------------------- | ------------------------------------------ |
| `(a)-[e]->(b)`                      | All edges from vertex a to b               |
| `(a)-[e1]->(b)-[e2]->(c)-[e3]->(a)` | 3-hop cycle                                |
| `(a)-[:transfer*0..]->(b)`          | 0 or more `transfer` edges from a to b     |
| `(a)-[:transfer*1..4]->(b)`         | Between 1 to 4 hops along `transfer` edges |

Use **constraints** (like `WHERE a.name = 'Nikita'`) to narrow results.

---

## 📊 Analyzing Graphs

Graph analysis reveals structure and influence inside your data.

### 🧠 Built-in Graph Algorithms:

| Category                | Algorithms & Use Cases                              |
| ----------------------- | --------------------------------------------------- |
| **Community Detection** | Find strongly or weakly connected clusters          |
| **Ranking**             | PageRank, Betweenness Centrality — detect influence |
| **Path Planning**       | Shortest paths (e.g., Bellman-Ford algorithm)       |
| **Structure Analysis**  | Find cycles, patterns, subgraphs                    |

> Use prebuilt APIs (e.g., `analyst.pagerank(graph_name)`) to apply analysis quickly.

---

### 🏦 Bank Example:

1. Create `bank_graph` from accounts + transfers
2. Run `PageRank` → assigns a score to each node (e.g., red = high rank)
3. Query: Find **cycles** that include **highly ranked vertices**

This combined **analysis + pattern query** helps detect suspicious activity.

---

## 👁️ Visualizing Graphs

Graphs are best **seen** to understand relationships.

### ✨ Oracle Graph Studio:

* Built into **Autonomous Database**
* Use the **Graph Studio notebook**:

  * Run PGQL queries
  * See visual outputs (nodes, edges, highlights, rankings)
* Helpful for exploring:

  * Community structure
  * PageRank results
  * Transaction trails
  * Suspicious cycles

---

## ✅ Final Takeaways

| Task            | Tool/Feature                                  |
| --------------- | --------------------------------------------- |
| Create Graph    | Automated modeler or PGQL DDL                 |
| Query Graph     | Property Graph Query Language (PGQL)          |
| Analyze Graph   | Prebuilt algorithms (PageRank, Shortest Path) |
| Visualize Graph | Oracle Graph Studio (notebook interface)      |

> 🧠 Graphs help uncover **patterns**, **anomalies**, and **relationships** not visible in traditional tabular data.
