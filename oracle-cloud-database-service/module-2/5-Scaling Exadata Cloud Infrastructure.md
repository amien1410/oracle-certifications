## 📈 Scaling Exadata Cloud Infrastructure

---

### 🚀 Flexible Scaling with Exadata X8M and Newer

The **flexible Exadata system model** (starting with **X8M**) is designed for **in-place scaling**—no need to migrate to a larger system shape.

You can **dynamically scale up or scale down**:

- 🖥️ **Database servers**
- 📦 **Storage servers**

This provides elasticity for handling growing workloads or optimizing costs during low-demand periods.

---

### ⚙️ Scaling Up Resources

To scale up, follow these steps:

1. Navigate to **Exadata Infrastructure Details**.
2. Under **Exadata Resources**, click **Scale Infrastructure**.
3. Select the desired number of **database** or **storage servers**.

✅ After provisioning:

- For **database servers**: Add newly available **OCPUs and memory** to VM clusters.
- For **storage servers**: 
  - Click **Add Storage Capacity** (banner will appear).
  - This triggers **rebalance** of data across existing storage infrastructure.
  - This **does not** auto-allocate storage to VM clusters—it just makes it **available**.

📌 **Result Example**:
> Storage expands from **190 TB** ➜ **254 TB**, visible under *Exadata Resources*.

---

### 📉 Scaling Down Resources

You can scale down resources **only in public cloud deployments**:

- **Database server**: Can be removed **only** if it has **no active VMs**.
- **Storage server**: Can be removed **only** if it was **not used** to expand storage previously.

For **older fixed-shape deployments** (X6, X7, X8):

- Scaling **requires migration** to a newer/larger shape.
- No in-place scaling supported for those models.

---

### 💡 Notes on Storage Expansion

- The **Add Storage Capacity** action **only rebalances** data across the storage servers.
- It does **not automatically resize** or allocate additional storage to VM clusters.
- You **must manually configure** storage groups or filesystems to utilize expanded capacity.

---

### 🧠 Summary

| Operation           | Notes |
|--------------------|-------|
| **Scale Up DB Servers** | Add OCPUs & memory to VM clusters |
| **Scale Up Storage**    | Click *Add Storage Capacity* to rebalance |
| **Scale Down DB Servers** | Only if no VMs are active |
| **Scale Down Storage**   | Only if unused for previous expansion |
| **Fixed-Shape Models**   | Must migrate to scale |
| **Public Cloud Only**    | Scale-down supported only in public deployments |

With Exadata’s flexible infrastructure, you can **scale elastically** to meet your application needs while optimizing **cost and performance**.
