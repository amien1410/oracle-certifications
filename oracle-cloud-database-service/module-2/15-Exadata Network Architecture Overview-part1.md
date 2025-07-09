# 🌐 Exadata Network Architecture Overview Part 1

👋 Hello! In this module presented by **Nicolas Cusato (Oracle)**, we explore the **network architecture** and supporting components of the **Exadata Database Service**, which can operate either:

- In the **Oracle Public Cloud** on **dedicated Exadata Cloud Infrastructure**, or  
- On-premises with **Exadata Cloud@Customer (C@C)**.

---

## 🎯 Learning Objectives

After completing this module, you’ll be able to:

✅ Describe the **network architecture** of Exadata Database Service  
✅ Provision the **Exadata Infrastructure** in the public cloud  
✅ Create and configure the **Exadata VM Cluster**  
✅ Understand the **storage configuration** options for VM Clusters

---

## 🧭 Exadata Network Architecture Components

The Exadata network is structured into **multiple layers**, optimized for both **performance** and **isolation**. Here’s a breakdown of the essential elements:

### 🧱 Infrastructure Layers

| Layer                         | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| **Dom0**                     | Oracle-managed VM for infrastructure control                               |
| **DomU**                     | Customer-managed VM(s) hosting Oracle Databases                            |
| **VM Cluster**               | Group of VMs running the databases                                         |

---

## 📡 Key Network Types

### 1. **Client Network**
- 🔗 Connects compute servers (VMs) to the **customer’s existing network**
- 🧭 Used for:
  - Application access via **SCAN** (Single Client Access Name)
  - **RAC VIPs** for cluster communication
- 💡 Requires:
  - **2 IPs per compute server**
  - **3 SCAN IPs**
  - **3 reserved IPs**

---

### 2. **Backup Network**
- 💾 Handles **backup traffic** and **bulk data transfers** independently from client traffic
- 🧬 Uses **2 NICs per server** (just like client network)
- 💡 Requires:
  - **1 IP per compute server**
  - **3 reserved IPs**

---

### 3. **Oracle Cloud Operations Network**
- 🔒 Dedicated to Oracle Operations for infrastructure maintenance and automation
- 📛 **Not accessible by customers**
- 📡 Bandwidth: **1 Gbps**

---

### 4. **RoCE Fabric Network**
- 🖧 **RDMA over Converged Ethernet** replaces older InfiniBand tech
- 🔄 Connects database and storage servers
- ⚙️ Each server uses:
  - **2 RoCE interfaces (RE0, RE1)** for redundancy
  - Connected to **separate RoCE switches**
- 🔧 Used for:
  - **Oracle RAC cluster interconnects**
  - **Data access from Exadata storage**

---

## 🌐 Network IP Planning Essentials

To integrate with your **corporate network**, you must plan and assign:

- 🔢 **Hostnames and IPs** for all client and backup interfaces
- 🧠 Proper **DNS and NTP** configurations (covered later)
- ⚠️ IPs **must not conflict** with any in-use address in your network

---

## 📝 Summary

The **Exadata Database Service network** is designed to:

- Support **high throughput**
- Ensure **network isolation**
- Enable **scalable cluster communication**
- Provide **secure Oracle-managed automation**
