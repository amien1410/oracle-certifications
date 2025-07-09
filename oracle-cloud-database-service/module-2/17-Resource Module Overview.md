# ⚙️ Provisioning Exadata Database Service – Resource Module Overview

Welcome to the next section of our journey into the Oracle Exadata Database Service! 🎓 In this module, we dive into the **key resources** used to provision and manage Exadata services—covering infrastructure, VM clusters, and access control.

---

## 📦 Required Resources for Provisioning

To launch the **Exadata Database Service**, after configuring your **networking prerequisites**, you must provision two primary OCI resources:

### 1. **Cloud Exadata Infrastructure**
- Manages:
  - 🧰 Infrastructure setup
  - 🗃️ Database and storage servers
  - 🔁 Infrastructure maintenance schedules
  - ➕ Expansion (scale-out) of DB and storage servers

### 2. **Cloud VM Cluster**
- Manages:
  - 🌐 Networking (client/backup)
  - 🛠️ Grid Infrastructure
  - 💾 OS, Database Homes, Databases
  - ⚖️ IORM (IO Resource Management)
  - 🧠 OCPU scaling (up/down)

---

## 🔐 Security Access with IAM

To **use OCI services**, including provisioning Exadata, users must have appropriate **Identity and Access Management (IAM) policies**.

- Access applies to all tools: **Console, REST API, CLI, SDKs**
- 🚫 If you see a **"Permission Denied"** or **"Unauthorized"** error:
  - ✅ Check with your **tenancy administrator**
  - 📜 Review your **IAM policies** for resource access rights

---

## 🖥️ Navigating the OCI Console

### 🎛️ Accessing Exadata Services:
1. Use the **navigation menu** (☰) in the upper left
2. Select: **Oracle Database > Exadata Database Service**

### 🌍 Region Selection:
- Use the **top-right region selector** to:
  - Choose your **deployment region**
  - Switch between regions as needed

### 🏗️ Deployment Models:
When accessing Exadata services via the Console, you will be prompted to choose between:

| Model                   | Location              |
|------------------------|-----------------------|
| **Exadata on Oracle Cloud** | In Oracle Public Cloud |
| **Exadata Cloud@Customer** | In your data center     |

> 💡 Each model offers similar automation but differs in **physical deployment** and **network configuration**.

---

## ✅ Summary

To provision the Exadata Database Service:
- Start by provisioning **Cloud Exadata Infrastructure**
- Then create a **Cloud VM Cluster**
- Ensure **IAM permissions** are in place
- Use the **OCI Console** for setup and management
- Choose the appropriate **deployment model** for your business needs
