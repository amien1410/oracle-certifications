# 📘 Oracle Base Database Service – VM Shapes, Storage, Availability & Security

👩‍🏫 *Module 2: Compute Shapes, Storage Architecture, HA Strategies, and Defense in Depth*

---

## 🖥️ Compute Shapes for DB Systems

Oracle offers **4 compute shape types** for various workloads:

### 1. 🔹 Ampere Flexible Shape (A1)

- **Economical** option
- ✅ Supports: *Single-node DB only*  
- ❌ Does **NOT** support Oracle Database Standard Edition
- CPU: **1–57 OCPUs**, Memory: **8 GB/OCPU**
- Network: **1 GB/s per OCPU**, up to 40 GB/s

### 2. 🔹 Intel Flexible Shape

- ✅ Supports: *Single-node and 2-node RAC*
- ✅ Supports Standard and Enterprise Edition
- CPU: **1–32 OCPUs**, Memory: **16 GB/OCPU**
- Network: **1 Gbps per OCPU**, up to 32 Gbps

### 3. 🔹 AMD Flexible Shape

- ✅ Supports: *Single-node and 2-node RAC*
- ✅ Supports Standard and Enterprise Edition
- CPU: **1–64 OCPUs**, Memory: **16 GB/OCPU**
- Network: **1 Gbps per OCPU**, up to 40 Gbps

### 4. 🔹 Fixed Shape (Legacy)

- CPU: **1–24 OCPUs**, Memory: **15 GB/OCPU**
- ❗ To scale, you must **change the shape entirely**

> 🚫 **Single → RAC scaling is not supported**. Choose the right shape at launch!

---

## 💾 Storage Architecture Options

Choose between:

### 1. 🔸 **Logical Volume Manager (LVM)**  
- ✅ Supported for *single-node*
- ✅ Allows *fast provisioning*

### 2. 🔸 **Automatic Storage Management (ASM)** *(Default)*
- ✅ Supported for *single-node and 2-node RAC*
- Uses **Oracle Grid Infrastructure**
- **80%** of disk → Data  
  **20%** of disk → RECO  
- **External redundancy** (OCI Block Storage has triple mirroring)
- Cloning supported on both **LVM** and **ASM**
- Storage is **scalable online** post-deployment

---

## 🌐 High Availability (HA) & Disaster Recovery (DR)

Oracle leverages the following **OCI regions & domains** for HA:

- **Fault Domains**: Isolate VM nodes in separate physical servers
- **Availability Domains**: Used to distribute resources across a region
- **Regions**: Enable DR with **Data Guard** replication across geographies

### 🔁 Oracle Maximum Availability Architecture (MAA) Stack

| Feature                | Availability                             |
|------------------------|------------------------------------------|
| Flashback              | All tiers                                |
| Backup & Recovery      | All tiers                                |
| Multitenant (≤3 PDBs)  | All editions                             |
| Multitenant (>3 PDBs)  | HP & XP licenses (up to 4,098 PDBs)      |
| Data Guard             | Enterprise Edition and above             |
| Active Data Guard      | Extreme Performance only                 |
| RAC                    | Extreme Performance only                 |
| Application Continuity | Extreme Performance only                 |

> ✅ Built-in **Oracle Best Practices** optimize performance, security, and availability via automation.

---

## 🔐 Defense in Depth: Cloud Security Strategy

Oracle embeds security at every layer of the stack using a **concentric model** of protection:

### 🧱 Data Protection Tools

- **Transparent Data Encryption (TDE)** – Encrypt data at rest
- **Data Redaction & Masking** – Limit data exposure
- **OCI Vault** – Separates control of encryption keys
- **Database Vault** – Prevents DBAs from querying user data
- **Database Firewall** – Controls executable SQL
- **Data Safe** – Tracks, audits, and alerts on risky behavior

### 🛡️ Access & Infrastructure Security

- Minimal OS packages to reduce attack surface
- Token-based SSH login to VMs
- OCI Virtual Cloud Network (VCN) for isolation
- Native encryption for all client-database communication
- Integrated IAM for fine-grained control

---

## 🔎 Oracle Data Safe: Centralized Security Hub

Included **at no extra cost**, Oracle Data Safe helps with:

- 🧪 **Security assessments** – Detect misconfigurations and risks
- 👤 **User behavior auditing** – Identify and alert on risky actions
- 🔍 **Sensitive data discovery** – Know what and where your sensitive data is
- 🛡️ **Masking tools** – Protect dev/test environments
- 📊 **Dashboards & reports** – Central security visibility

> ⏱️ **Quick setup** – Easy to use, up and running in under an hour, no deep security knowledge required

---

## ✅ Summary Highlights

- Choose from **4 flexible or fixed VM shapes** based on cost, power, and HA needs
- Select **LVM or ASM** for storage architecture – ASM is default & required for RAC
- Leverage **OCI HA constructs** + MAA stack (Flashback, RAC, Data Guard) for resilient deployments
- Embrace Oracle’s **Defense in Depth** with powerful, automated security
- Use **Data Safe** for smart, simplified, and proactive database protection

---

👨‍🎓 *With this knowledge, you're ready to make informed architecture and security decisions when provisioning Oracle Base Database Services in the cloud.*
