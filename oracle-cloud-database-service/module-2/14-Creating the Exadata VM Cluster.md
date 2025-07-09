# 🧱 Creating the Exadata VM Cluster (Cloud@Customer)

Now that the **Exadata VM Cluster Network** has been successfully created, the next step is to **provision the Exadata VM Cluster** on the **Cloud@Customer (C@C)** infrastructure. This VM Cluster is the **core compute layer** where Oracle databases will reside and operate.

---

## 🔗 What is the VM Cluster?

The **VM Cluster** acts as the **logical host** for your Oracle Databases, built on top of the **Exadata infrastructure**. It includes:

- Oracle **Grid Infrastructure**
- Oracle **Database software**
- VM compute resources

It serves as the **deployment target** for all databases created on the Exadata C@C.

---

## ⚙️ Key Configuration Parameters

When provisioning the VM Cluster, you must define:

| Parameter               | Purpose                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| 🧠 **OCPUs**             | Number of **enabled CPU cores** for compute resources                   |
| 💾 **Memory per VM**     | RAM allocated to each virtual machine (minimum 30 GB/VM)                |
| 📂 **Local Storage per VM** | Local file system size per VM (minimum 60 GB/VM)                        |
| 📦 **Exadata Storage**   | Amount of **shared Exadata Storage** allocated to the cluster           |
| 🌐 **VM Cluster Network** | Previously created network config (must be associated during setup)     |

---

## 🛑 Pre-requisites

Before you can create a VM Cluster:

- ✅ You **must have already created** a **VM Cluster Network**
- ✅ That network **must be linked** to the new VM Cluster
- ✅ You should have defined IPs, hostnames, and DNS registration as part of the network setup

---

## 🏁 Summary

The **VM Cluster** is essential to:

- Hosting Oracle databases
- Managing compute, memory, and storage usage
- Enabling advanced Exadata performance capabilities

➡️ Once created, you'll be ready to **deploy databases** on your Exadata Cloud@Customer system.

Next up: **Provisioning Databases within the VM Cluster**
