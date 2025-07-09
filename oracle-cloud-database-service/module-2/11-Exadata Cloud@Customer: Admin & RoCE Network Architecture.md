# 🌐 Exadata Cloud@Customer: Admin & RoCE Network Architecture

In this section, we explore the **admin** and **RDMA over Converged Ethernet (RoCE)** networks within the **Exadata Cloud@Customer (C@C)** infrastructure and how they integrate with your data center environment.

---

## 🧩 Admin Network Overview

- The **Admin interfaces** are **preconfigured** to connect to an **Ethernet switch** inside the Exadata C@C rack.
- These interfaces are **used for system administration and internal communication** between components.
- Fully contained within the **C@C rack**; no direct exposure to your corporate LAN.

---

## 🚀 RoCE Network (RDMA over Converged Ethernet)

### 🔄 Replaces InfiniBand

The **RoCE network** has replaced the older **InfiniBand** fabric, offering faster and more efficient connectivity.

### 🧠 Purpose of RoCE:
- Facilitates **Oracle RAC interconnect** traffic
- Supports **data access** to Exadata Storage Servers
- Powers **high-speed internal communication** within the rack

### 🔗 Connections:
Each server (DB, storage, control plane) has:
- **2 RoCE interfaces**
- Connected to **2 separate RoCE switches** in the Exadata rack for **redundancy**

> 🛑 The RoCE network is **non-routable** and fully **isolated** within the C@C rack.

---

## ⚠️ IP Address Planning Considerations

### ❗ Avoid IP Conflicts
- **RoCE and Admin networks** must have **non-overlapping** IP ranges
- IPs **must not conflict** with existing ranges in your corporate network

---

## 🧾 Hostnames and IP Requirements

- You must define **hostnames and IP addresses** for:
  - **Client interfaces**
  - **Backup interfaces**
  - Other internal network components
- Register all client and backup hostnames/IPs in your **corporate DNS**

---

## 🕒 DNS & NTP Configuration

To ensure system stability and synchronization, Oracle requires:

| Requirement | Minimum | Maximum |
|------------|---------|---------|
| **DNS Servers** | 1 | 3 |
| **NTP Servers** | 1 | 3 |

- These servers must be:
  - Accessible by **control plane servers**
  - Reachable from the **client network**
- NTP ensures that **all system components remain time-synchronized**, which is critical for Oracle RAC and data consistency.

---

📌 **Summary**:
- Admin and RoCE networks are internal to the C@C rack but require careful IP planning
- RoCE provides a high-speed, redundant fabric for RAC and storage traffic
- Accurate DNS and NTP setup is essential
- Ensure hostnames/IPs for client and backup networks are properly registered

➡️ Coming Up: VM Cluster Network creation & provisioning the Exadata VM Cluster.
