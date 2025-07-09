# 🌐 Creating the Exadata VM Cluster Network (Cloud@Customer)

Before provisioning a **VM Cluster** on the **Exadata Cloud@Customer (C@C)** infrastructure, you must first create a **VM Cluster Network**. This is a critical foundational step that links your **on-prem Exadata hardware** to the databases you’ll deploy on it.

---

## 🧩 What is the VM Cluster Network?

The **VM Cluster Network** serves as a bridge between:

- The **Exadata C@C infrastructure** in your data center
- The **Oracle VM Clusters** that host your databases

It defines **network configurations and allocations** such as:

- IP addresses
- Hostnames
- Subnets for client and backup traffic

---

## 🏗️ Why is it Needed?

You **must** create a VM Cluster Network **before**:

- Creating any VM cluster
- Deploying databases

Because the **Exadata Cloud@Customer** system is **physically deployed in your data center**, these network configurations are **not part of a cloud-based VCN**. Instead, they **originate from your on-prem network resources**.

---

## 📐 Key Components

| Component        | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Client Subnet** | Used by application clients to access the databases                        |
| **Backup Subnet** | Used for database backups over your internal network                       |
| **Hostnames/IPs** | Must be pre-registered in your corporate **DNS** system                    |

---

## 🔁 Reusability & Limitations

- ✅ You can create **multiple VM Cluster Networks** on a single infrastructure
- ❗ However, **each VM Cluster Network can only be linked to one VM cluster**

---

## 🚀 What’s Next?

Once the **VM Cluster Network** is created:

- You can **proceed with VM cluster provisioning**
- From there, manage and scale Oracle databases just like you would in **Exadata Database Service on Oracle Public Cloud**

➡️ Coming up next: **Provisioning the Exadata VM Cluster**
