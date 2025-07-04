# 📘 Oracle Autonomous Database: Dedicated Infrastructure

**Instructor:** Linda Foinding
**Topic:** Autonomous Database Dedicated Infrastructure
**Platform:** Oracle University

---

## 🚀 Overview

Oracle Autonomous Database offers **two deployment options**:

1. **Serverless** – Fully managed by Oracle, ideal for ease of use and automation.
2. **Dedicated** – Private database cloud with customizable control, running on dedicated Exadata infrastructure.

---

## 🧠 Key Concepts

### 🛠️ Serverless Deployment

* **Fully automated:** Provisioning, tuning, backup, scaling, etc.
* **Elastic scaling:** Instantly scales compute & storage based on workload.
* **User input:** Select DB type (OLTP/OLAP), region, and base resources.

---

### 🏢 Dedicated Deployment

* **Private cloud** on dedicated **Exadata** within:

  * Oracle Public Cloud
  * Customer’s data center (**Cloud\@Customer**)
* **Ideal for:**

  * Consolidating databases of various types & sizes
  * Enterprises offering DBaaS (Database as a Service)
* **Isolation:** Complete isolation from other tenants

---

## 🔒 Key Benefits of Dedicated Infrastructure

| Feature               | Description                                                            |
| --------------------- | ---------------------------------------------------------------------- |
| **Isolation**         | Fully dedicated compute, storage, network                              |
| **Custom Policies**   | Control update schedules, workload separation, availability, backup    |
| **Security**          | Default private subnet (no internet access), VCN & FastConnect support |
| **Lifecycle Control** | Greater control over patching and resource management                  |
| **Flexible Topology** | Define Autonomous VM Clusters (AVMCs) and Container DBs (ACDs)         |

---

## 🖧 Network & Access

* Uses **VCN (Virtual Cloud Network)** with **private subnets**
* Network services: FastConnect, IPSec VPN, Subnet Peering
* **Cloud\@Customer** offers strict **data sovereignty** and **behind-firewall** deployment

---

## ☁️ Cloud\@Customer Highlights

* **Exadata** delivered inside customer data centers
* Cloud automation with **local + remote control planes**
* **Secure tunnel** for OCI operations and patching
* **Performance:** Up to

  * 45× SQL read IOPS
  * 40× SQL throughput
  * 98% lower latency vs. AWS RDS Outposts
* **Management:** OCI Console & APIs (when online), but **databases remain usable even offline**

---

## 🛡️ Security & Encryption

* **TDE (Transparent Data Encryption):** Encrypts data at rest automatically
* **Authorized users** see decrypted data seamlessly

---

## 🔁 Backup Options

* On-premises storage
* Zero Data Loss Recovery Appliance
* Locally-mounted NFS
* Oracle Public Cloud storage

---

## 🧩 Compatibility

Autonomous Database Dedicated runs on the same **Exadata** as:

* **Exadata Database Service**
* **Exadata Cloud\@Customer**
* Integrates with **Oracle at Azure** (Exadata, ADB Serverless, RAC, Data Guard)

---

## 💡 Summary

| Feature         | Serverless       | Dedicated                   |
| --------------- | ---------------- | --------------------------- |
| Automation      | ✅                | ✅                           |
| Isolation       | ❌                | ✅                           |
| Custom Policies | ❌                | ✅                           |
| Public Access   | ✅                | ❌ (private subnet)          |
| Control         | Low              | High                        |
| Ideal For       | Simple use cases | Enterprise workloads, DBaaS |

---

## 🏁 Final Notes

Oracle's **Autonomous Database Dedicated Infrastructure** empowers organizations with:

* Customizable control
* Private cloud capabilities
* High performance & security
* Seamless management via OCI or behind firewall with **Cloud\@Customer**

---

**Thanks for learning!**
🔒💻🧠📊

---
