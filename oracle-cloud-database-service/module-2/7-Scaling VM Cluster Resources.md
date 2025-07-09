# 📌 Exadata VM Cluster Scaling Notes

## 🔧 Scaling VM Cluster Resources

Exadata Database Service enables online scaling of VM cluster resources (OCPU, memory, storage) to adapt to business demands.

### ✅ How to Scale

1. **Navigate to Cluster Details**
2. **Initiate "Scale VM Cluster" Action**
3. **Adjust per VM allocation:**

   * **OCPUs**
   * **Memory** (≥30 GB, multiple of 1 GB)
   * **Local File System** (≥60 GB, multiple of 1 GB)

> ⚠️ Changes <2% from current value are ignored to prevent unnecessary disruption.

### 💡 Key Notes:

* OCPU billing is separate from infrastructure charges.
* OCPUs can be scaled to **zero** to shut down compute servers (infra billing still applies).
* To restart, allocate at least **2 OCPUs/VM**.
* Scaling memory or file system triggers **rolling reboot** of compute servers.
* **Database Instance Caging**: Update `CPU_COUNT` manually when scaling OCPUs.

---

## 🗄️ Scaling Exadata Storage for VM Cluster

* Storage allocation minimum: **2 TB**, increment by **1 TB**
* Storage is **evenly distributed** across available storage servers
* You can **reduce** storage allocation if:

  * Current contents fit in new size
  * There is still space for growth

---

## 🔄 Multi-VM & Node Subsetting

### 🌐 Multi-VM:

Allows creation of multiple VM clusters on the same infrastructure.

**Benefits:**

* **Security separation**: Separate dev/test/prod clusters
* **Maintenance isolation**
* **Failure isolation**
* **VLAN-level network isolation**
* **Admin separation**

### 🧩 Node Subsetting:

Run a VM cluster on a **subset of DB servers**

**Benefits:**

* Efficient resource usage
* Tailored clusters for different workloads
* Lower costs (only pay for used OCPUs)
* BYOL efficiency

---

## 🛠️ Creating VM Clusters with Multi-VM + Subsetting

1. Go to **Exadata Cloud Infrastructure Details**
2. Click **Create VM Cluster**
3. Under **Configure VM Cluster**, click **Change DB Servers**
4. Choose DB servers for VM placement (view per-server resource usage)
5. Set:

   * **OCPUs/VM**
   * **Memory/VM**
   * **Local File System/VM**
6. Click **Create Exadata VM Cluster**

---

## 🔽 Shrinking a VM Cluster

1. Go to the cluster detail page
2. In the VM list, click **Actions** → **Terminate VM**
3. Confirm by entering the VM name
4. Click **Remove**

> ⚠️ Terminating a VM **deletes any database instances** running on it!

---

📚 **Summary:**
Oracle's Exadata Database Service offers robust and flexible VM cluster scaling through an intuitive interface and automation. Combining online scaling, Multi-VM, and Node Subsetting delivers tailored, cost-efficient, and secure database environments.

---

✍️ *Created by an elite, diligent student taking awesome notes.*
