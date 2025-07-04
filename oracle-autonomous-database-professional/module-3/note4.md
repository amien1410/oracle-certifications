# 📘 OCI Policies for Oracle Autonomous Database Dedicated

**Instructor:** Linda Foinding
**Lesson Topic:** Creating and Managing OCI IAM Policies for Autonomous Dedicated Deployment
**Platform:** Oracle University

---

## 🧭 Purpose

This lesson explains how to design and apply OCI Identity and Access Management (IAM) **policies** for managing Autonomous Database Dedicated infrastructure. It focuses on separating duties between **Fleet Administrators**, **DBAs**, and **Developers** in a secure and organized manner.

---

## 👥 Roles and Responsibilities

### 1. **Fleet Administrators**

* **Duties:**

  * Allocate budgets using **compartments**
  * Provision:

    * Exadata Infrastructure
    * Autonomous VM Clusters (AVM)
    * Autonomous Container Databases (ACD)
* **OCI Access Required:**

  * Full `manage` permission on:

    * Exadata Infrastructure
    * AVM
    * ACD
    * Required Networking Resources

### 2. **Database Administrators (DBAs)**

* **Duties:**

  * Create, monitor, and manage:

    * **Autonomous Databases (ADB)**
    * **Oracle users** inside those databases
  * Provide connection details to Developers
* **OCI Access Required:**

  * `manage` on:

    * Autonomous Databases
    * Autonomous Backups
    * Use access to ACDs and networking resources

### 3. **Developers / Database Users**

* **Duties:**

  * Use Autonomous Databases for application development
* **OCI Account:** Not required
* **Access:** Through connection details shared by DBAs

---

## 🧩 Resource Types

| Resource                         | Description                                |
| -------------------------------- | ------------------------------------------ |
| `cloud-exadata-infrastructures`  | Dedicated Exadata hardware                 |
| `cloud-autonomous-vm-clusters`   | VM clusters for workload/network isolation |
| `autonomous-container-databases` | Container runtime for Autonomous Databases |
| `autonomous-databases`           | Actual DB instances used by applications   |
| `autonomous-backups`             | Backup archives for ADBs                   |

---

## 🛡️ IAM Policy Syntax

```hcl
Allow group <GROUP_NAME> to <VERB> <RESOURCE> in compartment <COMPARTMENT_NAME>
```

| Verb    | Description                                |
| ------- | ------------------------------------------ |
| inspect | Limited read-only (auditors)               |
| read    | Full read-only access                      |
| use     | Read + invoke actions (no create/delete)   |
| manage  | Full access (read, create, update, delete) |

---

## 🧪 Policy Example: Acme Corporation

### 🔹 Groups:

* `AcmeFA` – Fleet Admins
* `RoadrunnerDBA` – DBAs for Roadrunner business unit
* `CoyoteDBA` – DBAs for Coyote business unit

### 🔹 Permissions:

* **AcmeFA group (Fleet Admins)**:

  ```hcl
  Allow group AcmeFA to manage cloud-exadata-infrastructures in compartment FA
  Allow group AcmeFA to manage cloud-autonomous-vm-clusters in compartment FA
  Allow group AcmeFA to manage autonomous-container-databases in compartment FA
  ```

* **RoadrunnerDBA & CoyoteDBA groups (DBAs)**:

  ```hcl
  Allow group RoadrunnerDBA to manage autonomous-databases in compartment RoadrunnerDBA
  Allow group RoadrunnerDBA to manage autonomous-backups in compartment RoadrunnerDBA

  Allow group CoyoteDBA to manage autonomous-databases in compartment CoyoteDBA
  Allow group CoyoteDBA to manage autonomous-backups in compartment CoyoteDBA
  ```

* **Cross-group Access to Container DBs**:

  ```hcl
  Allow group RoadrunnerDBA to read autonomous-container-databases in compartment FA
  Allow group CoyoteDBA to read autonomous-container-databases in compartment FA
  ```

This allows DBAs to create Autonomous Databases inside the shared ACDs created by Fleet Admins.

---

## ⚙️ Operational Interfaces

Autonomous Database services can be managed through:

* **OCI Console (UI)**
* **OCI CLI**
* **REST APIs**
* **Language SDKs**: Java, Python, Go, Node.js

---

## 🧠 Key Takeaways

* OCI IAM Policies provide **fine-grained access control** to database infrastructure.
* Use **separate groups and compartments** for cleaner governance.
* Only **Fleet Admins** manage infra (Exadata, AVM, ACD); **DBAs** manage databases (ADB, backups).
* **Developers** access DBs using credentials, no OCI account needed.
* Roles and resources are aligned to business units for scalability and security.

---
