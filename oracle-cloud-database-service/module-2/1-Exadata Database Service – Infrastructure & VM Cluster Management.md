## 🖥️ Exadata Database Service – Infrastructure & VM Cluster Management

---

### 🎯 Objectives

By the end of this section, you will be able to:

- Describe Exadata management roles and responsibilities
- Schedule Oracle-managed infrastructure maintenance
- Scale infrastructure, VM clusters, and related resources
- Manage VM cluster components (OS, Grid Infrastructure, DB Homes)
- Understand IAM policies required for operations

---

### 🧱 Exadata Architecture Overview

| Layer                 | Managed By | Description |
|-----------------------|------------|-------------|
| **Infrastructure**    | Oracle     | Physical servers, storage, network fabric |
| **Guest VM (Compute)**| Customer   | VM OS, Grid Infrastructure, DB software, data |
| **Databases**         | Customer   | DB operations, patching, backups, scaling |

🛑 **Oracle does NOT have access to customer’s guest VMs.**  
🔐 Customers manage access, software installs, and encryption keys.

---

### 🔑 Key Concepts in Management

- **Infrastructure Resource**: Created first; includes physical hardware.
- **VM Cluster Resource**: Created after infrastructure; includes VMs where DBs run.
- **Management Interfaces**: Console UI, CLI, REST API, SDK

> ⚠️ Ensure you have **proper IAM policies** and **correct compartment selection** to perform tasks.

---

### 🧑‍💻 Management Operations – Roles & Tools

| Task                         | Tool(s)           | Notes                             |
|------------------------------|-------------------|-----------------------------------|
| Create infrastructure/cluster| UI, API, CLI       | Initial setup                     |
| Patch DB software            | User-managed      | Quarterly, within 180 days        |
| Patch Grid Infrastructure    | User-managed      | Customer-responsible              |
| Update VM OS                 | User-managed      | Done via OCI automation tools     |
| Infrastructure firmware etc. | Oracle-managed    | Scheduled quarterly maintenance   |
| Scale compute/storage        | User-managed      | Via UI/API                        |
| Delete or resize VM cluster  | User-managed      | Must meet IAM policy rules        |

---

### 🔧 Oracle-Managed Maintenance

Oracle applies **infrastructure-level patches** every quarter to:

- Compute servers (bare metal)
- Exadata Storage Servers
- Internal switches & RDMA fabric
- Power distribution units (PDUs)
- Firmware & control plane components

> 🕒 You can **schedule** your own maintenance window to align with business needs.

---

### 🔄 User-Managed Maintenance

As the customer, you are responsible for:

- 🔄 **Patching Grid Infrastructure**
- 🧩 **Patching Oracle Database software (DB Home)**
- 🛠️ **Updating VM Operating System**

🔁 Best Practice: Perform all tasks **quarterly** (max interval: **180 days**)

To perform these tasks, ensure you:

1. Have **OCI IAM permissions**
2. Use correct **compartment**
3. Use **OCI Console**, **API**, **CLI**, or **SDK**

---

### 🛡️ OCI IAM: Identity & Access Management

Five core IAM concepts:

| Concept     | Description |
|-------------|-------------|
| **User**    | Individual account |
| **Group**   | Collection of users |
| **Policy**  | Grants specific permissions |
| **Compartment** | Logical resource grouping |
| **Principle** | Who gets access (user/group) |

---

### 🗂️ IAM Policy Syntax Example

```plaintext
Allow group DBAdmins to manage database-family in compartment FinanceApps
````

* **Subject**: group DBAdmins
* **Verb**: manage
* **Resource Type**: database-family
* **Scope**: compartment FinanceApps

> 🔍 `database-family` includes Autonomous DBs, VM DB Systems, Exadata DB Services, and more.

---

### 🧰 Exadata Shapes

| Exadata Shape     | Notes                                                                  |
| ----------------- | ---------------------------------------------------------------------- |
| **X8/X8M/X9M**    | Use **VM Cluster resource model**                                      |
| **Legacy Shapes** | Use **DB System resource model** (migration to VM cluster recommended) |

---

### 💡 Summary

| Topic                              | Status |
| ---------------------------------- | ------ |
| Exadata Infra vs Guest VM roles    | ✔️     |
| Oracle-managed maintenance         | ✔️     |
| Customer-managed patching tasks    | ✔️     |
| IAM policies for DB and infra mgmt | ✔️     |
| Scaling and automation via OCI     | ✔️     |

Exadata Database Service gives full control to the customer inside guest VMs while Oracle ensures reliable infrastructure below the surface.
