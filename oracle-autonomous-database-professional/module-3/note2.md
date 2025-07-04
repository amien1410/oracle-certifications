# 📘 Oracle Autonomous Database: Dedicated Workflow & Functionality

**Instructor:** Linda Foinding
**Topic:** Workflow & Functionality of Autonomous Database Dedicated
**Platform:** Oracle University

---

## 🔄 Typical ADB Dedicated Workflow

### 👨‍✈️ Fleet Administrator Responsibilities:

1. **Provision Exadata Infrastructure**
2. **Create Autonomous VM Clusters (AVMs)**
3. **Set up Autonomous Container Databases (ACDs)**

### 👨‍💻 Developer/DBA Responsibilities:

* Provision databases inside ACDs (self-service model)
* May also create their own ACDs based on business needs

---

## 💰 Billing Breakdown

| Component               | Description                                                                      |
| ----------------------- | -------------------------------------------------------------------------------- |
| **Infrastructure Cost** | Based on Exadata infra size, number of DBs, storage servers                      |
| **Database Compute**    | Based on **active CPUs** consumed by running databases                           |
| ❗ Note                  | No charges for provisioning AVMs or ACDs — only **running databases** are billed |

---

## 🧱 Supported Exadata Infrastructure Models

* **X9M**
* **X10M** *(Elastic Shape)*
* **X11M** *(Elastic Shape, \~QTR Rack)*

Elastic shapes enable more granular scaling than fixed-size infrastructure.

---

## 🛠️ Getting Started: Setup Checklist

1. 🔼 **Request Service Limit Increase** for Exadata Rack
2. 👤 **Create Fleet Admin & DBA Roles**
3. 🏢 **Configure Private Cloud** (OCI compartments for IT and end users)
4. 🌐 **Design Network Topology**
5. ⚙️ **Provision Required Resources**:

   * AVMs (Autonomous VM Clusters)
   * ACDs (Autonomous Container Databases)
6. 👥 **Grant Access** to end users for provisioning ADB instances

---

## ⏱️ Subscription & Flexibility

* **Minimum subscription:** 48 hours
* **No ongoing cost** after unsubscribing
* Full control over:

  * Resource placement (for latency-sensitive workloads)
  * Patch scheduling
  * Software versioning
* **Migration options:**

  * Export/Import via **Object Store**
  * **Data Pump** or **GoldenGate**

---

## ⚖️ ADB Dedicated vs Serverless – Comparison

| Feature              | ADB Dedicated                   | ADB Serverless       |
| -------------------- | ------------------------------- | -------------------- |
| Infrastructure       | Private, single-tenant          | Shared, multi-tenant |
| Update Scheduling    | User-controlled (defer/skip)    | Oracle-managed       |
| DB Versions          | Multiple supported              | Fixed                |
| Sharding & In-Memory | ✅ Supported                     | ❌ Not available      |
| Replication          | Sync & Async, Active Data Guard | Limited              |
| User Tablespaces     | Customizable                    | Not customizable     |
| Connectivity         | Regular TCP (no wallet)         | Requires wallet      |
| Oracle ML Notebooks  | ❌ Not available                 | ✅ Available          |

---

## 🧠 Key Takeaways

* **ADB Dedicated** = Enterprise-grade control, flexibility, and isolation
* Best for:

  * Regulated environments
  * Development lifecycle separation
  * Custom patching/versioning
* Still retains **auto-scaling**, **cloning**, and **automation benefits** of Autonomous DB

---
