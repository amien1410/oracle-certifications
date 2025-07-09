# 🧰 Exadata Database Service: Lifecycle Management Notes

Welcome to this module on **lifecycle management** in Oracle Exadata Database Service. In this lesson, you'll learn how to manage key parts of the database lifecycle—from creating software images to deploying and managing databases (CDBs and PDBs).

---

## 📦 Key Learning Outcomes
You’ll learn how to:

- ✅ Create **custom database and grid infrastructure images**
- ✅ Create a **Database Home**
- ✅ Create a **database** (CDB with default PDB)
- ✅ Manage **Pluggable Databases (PDBs)**
- ✅ Enable **Data Guard**
- ✅ Perform **user-managed maintenance & upgrades**

---

## 🖼️ Creating Custom Software Images

Custom images allow you to standardize deployments with approved Oracle Database or Grid Infrastructure configurations.

### 🔹 Why Use Custom Images?
- Include specific:  
  - Database/Grid versions  
  - Release updates  
  - One-off patches  
  - Inventory contents
- Automate with Terraform and OCI workflows
- Create gold images per team/compartment (e.g., dev, test, prod)

### 🛠️ Steps:
1. Go to **Software Images** section in OCI Console
2. Click **Create Software Image**
3. Select:
   - `Database` or `Grid Infrastructure` image type
   - `Service type` (Exadata Database Service)
4. Choose:
   - Display name  
   - Compartment (can be different for dev/production separation)
5. Upload:
   - Release update  
   - Optional: upload Oracle Home inventory (for patch matching)
6. Click **Create Software Image**

Once created, the image is stored in Oracle-managed Object Storage and available for reuse in provisioning flows.

---

## 🏠 Creating a Database Home

1. Navigate to the **Exadata VM Cluster**
2. Under **Resources**, click **Database Homes**
3. Click **Create Database Home**
4. Provide:
   - Display name  
   - Choose software image (Oracle-provided or your custom image)
5. Click **Create**

> Note: Each DB Home is tied to a single software version and patch level.

---

## 🗄️ Creating a Database (CDB + PDB)

1. From the **VM Cluster Details** page, click **Create Database**
2. Input:
   - Database name  
   - Version  
   - Optional: PDB name
3. Choose an existing or new **Database Home**
4. Set **admin password** for `CIS` user
5. Configure **backup** options:
   - Destination  
   - Schedule
6. Choose encryption:
   - 🔐 Oracle-managed keys  
   - 🔐 Customer-managed keys (Vault)
7. Click **Create**

> If using Cloud@Customer, you can also integrate with **Oracle Key Vault (OKV)** for external key management.

---

## 🧩 Managing Pluggable Databases (PDBs)

- When a database is created, it includes:
  - 1 Container Database (CDB)  
  - 1 default Pluggable Database (PDB)

- Use Console, CLI, or API to:
  - Create additional PDBs  
  - Rename, unplug, plug, or drop PDBs  
  - Perform lifecycle management (clone, relocate, etc.)

---

## 📝 Summary

You now know how to:
- Create and manage **custom images** for consistent deployments
- Deploy **Database Homes** and **databases**
- Manage **pluggable databases (PDBs)** inside a container
- Customize with **encryption options**, **key management**, and **backups**
