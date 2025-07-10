## 🚀 Overview: Operating MySQL HeatWave Database System

MySQL HeatWave is the **only cloud database service** that combines:

- ✅ Transactional processing (OLTP)
- 📊 Real-time analytics across data warehouses and data lakes (OLAP)
- 🤖 Native in-database machine learning (ML)

All this is available **without the complexity and cost** of ETL duplication. Accessible via:
- **Oracle Cloud Infrastructure (OCI)**
- **Amazon Web Services (AWS)**
- **Microsoft Azure**

---

## 🔥 What is a HeatWave Cluster?

- A **HeatWave Cluster** consists of **1 or more nodes**
- Each node stores **up to 800GB of in-memory data**
- **Processes analytics & ML queries** at scale
- Queries meeting offload conditions are **automatically redirected** to HeatWave for acceleration

**Data Workflow:**
1. Query sent by application → MySQL Database
2. Offloaded to HeatWave Cluster (if eligible)
3. HeatWave processes → sends result back → MySQL returns to application

---

## 🛠️ Requirements Before Using HeatWave

Ensure you have:

- ✅ A MySQL DB system using shape `VM.Standard.E3` or `E264`
- ✅ A compute instance on a **public subnet in the same VCN**
- ✅ **MySQL Shell ≥ 8.0.22**
- ✅ Correct **IAM policies**, including `mysql-analytics`

---

## ➕ Add HeatWave Cluster to MySQL System

Steps:

1. Navigate to **OCI Console → MySQL → Database Systems**
2. Select your database → Click **Add HeatWave Cluster**
3. Configure:
   - 📦 **Shape** (OCPUs, RAM)
   - 🔢 **Node Count**
4. Use **"Estimate Node Count"** tool based on existing schema data
5. Click **Add HeatWave Cluster**

---

## 📥 Load Data into HeatWave

1. **Identify tables** to load
2. Exclude unsupported columns
3. Set `secondary_engine = RAPID` for each table
4. Execute `LOAD TABLE` command

🔄 Data is:
- Read from InnoDB
- Converted to columnar format
- Distributed **horizontally across nodes**
- Synced in real-time after updates

🧪 **Verify Load:**
Use HeatWave Performance Schema to check load status.

---

## 🔗 Connecting & Querying HeatWave

- Use standard **ODBC/JDBC** connectors
- Clients/apps connect to MySQL DB node
- MySQL optimizer offloads queries to HeatWave **only if**:
  - All functions are supported
  - HeatWave is faster than MySQL for that query

---

## 🤖 Built-In Machine Learning

**Use Case Example:**
E-commerce app auto-recommending products using an ML model trained **inside HeatWave** — no separate ML tool needed.

Features:
- 📈 Real-time predictions during transactions
- 🔍 Explainable AI
- ✅ No data movement = Higher Security + Compliance

---

## 🪵 MySQL HeatWave Lakehouse

Query **up to 500 TB** of data in various formats:
- `.CSV`, `.Parquet`, **Aurora/Redshift exports**
- Data **in object store**, not MySQL

🏆 **Industry first**: Querying object store data **as fast** as from MySQL!

---

## 🧰 Manage Your HeatWave Cluster

### ▶️ Start / Stop / Restart
- Navigate: **OCI → MySQL → Database Systems → HeatWave**
- Actions:
  - **Start**: Enables cluster
  - **Stop**: Pauses cluster + stops billing
  - **Restart**: Requires reload of in-memory data

### ❌ Delete Cluster
- Navigate: HeatWave resource section → Click **Delete**
- Note: This does **not delete your database system or data**
- However, deleting the DB system **will** delete the attached cluster

---

## 🧠 Key Benefits Recap

✅ Combines **OLTP + OLAP + ML** in one  
✅ Eliminates ETL complexity  
✅ High-performance **in-memory analytics engine**  
✅ Supports **real-time ML and analytics**  
✅ Enables **Lakehouse querying up to 500TB**  
✅ Fully managed on OCI, with **automated operations**  

MySQL HeatWave is your all-in-one powerhouse for next-gen data workloads.
