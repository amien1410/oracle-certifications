# 🔁 Migrating to Oracle Autonomous Database

**Instructor:** Michelle
**Lesson Objective:** Learn methods, tools, and best practices for migrating to Oracle Autonomous Database (ADB), including format, size, tools, and cloud integration.

---

## 📊 Migration Overview: How Data Flows into ADB

| Source             | Method                                      | Destination                     |
| ------------------ | ------------------------------------------- | ------------------------------- |
| Local/On-prem      | SQL Developer, SQL Loader, Data Pump        | Direct to ADB                   |
| Cloud Object Store | CSV, JSON, Parquet, Avro, etc.              | External or Loaded Table in ADB |
| Other Databases    | Data Pump, GoldenGate, DB Migration Service | Synced or Exported to ADB       |

---

## ✅ Preferred Data Loading Approach

1. **Stage data** in cloud **Object Storage** (preferably **Oracle**)
2. **Load or query directly** from ADB using tools like:

   * `DBMS_CLOUD`
   * `Data Studio`
   * `Data Pump`

---

## 🧰 Tools & Packages

| Tool/Package                   | Purpose                                                                                 |
| ------------------------------ | --------------------------------------------------------------------------------------- |
| **DBMS\_CLOUD**                | Move data securely from object storage to ADB. Supports AWS, Azure, Parquet, Avro, etc. |
| **SQL Loader**                 | Load local files (with OS/client limitations)                                           |
| **Data Pump**                  | Migrate and upgrade full or partial Oracle DB                                           |
| **SQL Developer**              | GUI for Data Pump, Excel import, etc.                                                   |
| **DBMS\_CLOUD\_ADMIN**         | Admin functions like configuring DB links or quotas                                     |
| **Zero Downtime Migration**    | Migration with minimal disruption                                                       |
| **Database Migration Service** | Fully managed online/offline migrations                                                 |

---

## ⚙️ Migration Considerations

| Consideration            | Explanation                                                      |
| ------------------------ | ---------------------------------------------------------------- |
| 📁 File Format           | JSON, CSV, Parquet, Avro, Excel all supported                    |
| 📦 File Size             | Use DBMS\_CLOUD for large files — no volume limit                |
| ☁️ Cloud Storage         | Oracle, AWS S3, Azure Blob all supported                         |
| 🔐 Security & Governance | Access controlled; audit and revoke available                    |
| 🌐 Network Latency       | Measure with tools like `cloudharmony.com` or Oracle’s dashboard |
| 🧠 Hints & Optimizers    | ADB ignores most SQL hints by default; can be re-enabled         |
| 📉 Compression           | Hybrid Columnar Compression used by default                      |
| 🔁 DML Impacts           | Frequent updates may reduce compression performance              |

---

## 🧭 Steps for a Smooth Migration

1. **Assess** existing DB using **Cloud Migration Advisor**
2. **Prepare** environment: remove unsupported features, convert to PDB, encrypt, etc.
3. **Choose Tool**:

   * **Data Pump**: for most full/partial DB migrations
   * **GoldenGate**: for real-time sync (online migration)
   * **SQL Developer**: for smaller tasks & file-based import
4. **Validate** using tools (e.g., GoldenGate’s compare tool)

---

## 📡 Supported Migration Types

| Source → ADB  | Migration Type            | Notes                     |
| ------------- | ------------------------- | ------------------------- |
| Oracle 10.1+  | ✅ Offline (Data Pump)     | Auto upgrade              |
| Oracle 12c+   | ✅ Online (GoldenGate)     | Real-time sync            |
| 3rd Party DBs | ✅ Indirect (Offline only) | Behind firewall supported |
| Within OCI    | ✅ Full support            | Direct connection best    |

---

## 🔎 DBMS\_CLOUD Highlights

* Supports:

  * Access to **external tables**
  * Full **data ingestion**
  * REST API interactions
* Works with:

  * Oracle Cloud
  * **AWS S3**
  * **Azure Blob**
* Supports formats like:

  * **Parquet**
  * **ORC**
  * **AVRO**

---

## 💡 Tips

* Use **external tables** for on-the-fly queries without full import.
* Gather table statistics manually if not using direct path load.
* Monitor latency before deciding ADB deployment region.
* Validate and test thoroughly using built-in tools after migration.

---

🎓 **End of Lesson:**
