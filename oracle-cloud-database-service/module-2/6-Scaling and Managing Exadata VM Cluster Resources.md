## 🧩 Scaling and Managing Exadata VM Cluster Resources

---

### 🔄 Online Scaling of VM Cluster Resources

With Exadata Database Service, you can **scale VM cluster compute resources** (CPU, memory, local storage) **online** to meet changing business needs—**without downtime**.

#### 🛠️ How to Scale a VM Cluster:

1. Go to **Cluster Details**.
2. Click **Scale VM Cluster**.
3. Adjust:
   - **OCPUs** (min 2 per VM)
   - **Memory** (≥ 30 GB, multiple of 1 GB)
   - **Local File System Storage** (≥ 60 GB, multiple of 1 GB)

📌 **Notes:**
- You can scale **OCPUs down to 0**, which shuts down the VM and suspends billing for compute (infra fees still apply).
- **Memory and storage changes under 2%** of current value are **ignored** to avoid unnecessary service interruptions.
- Changing **memory or storage** triggers **rolling reboots** to preserve service availability.

---

### 🧮 Scaling Exadata Storage for a VM Cluster

To adjust Exadata storage allocation:

- Go to **Configure Exadata Storage** during cluster setup or modification.
- Specify total usable storage (min: **2 TB**, in **1 TB** increments).
- ⚠️ Ensure new storage size is **enough to cover existing data** plus growth.

Storage is **evenly distributed** across storage servers.

---

### 🔀 Multi-VM and Node Subsetting

#### 🧱 What is Multi-VM?

**Multi-VM** allows multiple VM clusters to run on a single Exadata infrastructure.

🔒 **Use Cases:**
- **Environment separation** (e.g., dev/test/prod)
- **Data security isolation** (PCI/HIPAA)
- **Maintenance separation**
- **Failure containment**
- **Custom resource management**
- **Team-based administrative control**

---

#### ⚙️ What is Node Subsetting?

**Node Subsetting** = assign VM clusters to **only a subset** of DB servers.

🎯 **Benefits:**
- Tailored resource usage
- Right-sized clusters
- Cost optimization:
  - Pay only for **OCPUs in use**
  - Apply **BYOL** selectively
- Flexible expansion/shrinkage

---

### 🧑‍💻 How to Provision a VM Cluster with Node Subsetting

1. Go to **Exadata Infrastructure Details**.
2. Click **Create VM Cluster**.
3. Under **Configure VM Cluster**:
   - Click **Change DB Servers**.
   - Select which DB servers the new cluster will run on.

4. Set resource values:
   - **OCPUs**
   - **Memory**
   - **Local storage**

5. Complete remaining settings and click **Create Exadata VM Cluster**.

---

### ➕ Expand or ➖ Shrink VM Clusters

To **remove a VM**:

1. Go to the **VM Cluster Details** page.
2. Find the VM you wish to remove.
3. Click **Action → Terminate**.
4. Confirm VM name and click **Remove**.

⚠️ Terminating a VM also **terminates all databases** running on it.

---

### 📌 Summary

| Feature | Description |
|--------|-------------|
| **Scale OCPUs** | Per VM, 0 to N (min 2 for active) |
| **Scale Memory** | ≥ 30 GB, rolling reboot |
| **Scale Storage** | ≥ 60 GB per VM, rolling reboot |
| **Multi-VM Support** | Multiple clusters per Exadata infra |
| **Node Subsetting** | Allocate cluster to subset of DB nodes |
| **Add/Remove VMs** | Dynamically resize clusters |
| **Exadata Storage** | 2 TB min, 1 TB increments, shared |

These features offer **cloud elasticity** with **cost control**, **security isolation**, and **operational efficiency** for managing consolidated Oracle Database workloads.
