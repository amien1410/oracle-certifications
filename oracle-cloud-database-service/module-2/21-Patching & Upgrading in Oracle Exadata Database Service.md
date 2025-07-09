# 🔧 Patching & Upgrading in Oracle Exadata Database Service

In this section, we explore **how to patch and upgrade** various components of the Exadata Database Service VM Cluster, including:

- Oracle Grid Infrastructure (GI)
- Oracle Database Homes (DB Homes)
- The Databases themselves

---

## 🧱 Updating Grid Infrastructure (GI)

You can patch Oracle Grid Infrastructure (GI) on your VM cluster using:

- **OCI Console**
- **REST APIs**

### ✅ Steps:

1. Navigate to **Updates Page**.
2. Choose the **desired GI version**.
3. Use the **Actions icon** (⋮) to:
   - `Run Precheck`: Validate readiness
   - `Apply Patch`: Precheck + Patch if passed

⚙️ **Rolling Patching** is used:
- One node is patched at a time
- Database instances on that node will **temporarily go offline**

📌 **Precheck** is **strongly recommended** before maintenance windows.

---

## 🗃️ Updating Database Homes (DB Homes)

Two patching options:

### Option 1: Update Existing DB Home
- Updates all databases using the DB Home
- Done in a **rolling** manner across RAC nodes

### Option 2: Move Database to New DB Home ✅ _Recommended_
- Create a new DB Home with the desired patch
- Move databases individually (less downtime)

### 📋 Patch Steps:

1. From **Updates Page**, pick patch for:
   - Oracle-provided image, or
   - Custom database software image
2. Click **Run Precheck**
3. Click **Apply Patch** if passed

---

## 🚚 Moving a Database to Another DB Home

This is the **easiest and least disruptive** way to patch a database.

1. Go to the **Database Details** page
2. Click `Move to Another Database Home`
3. Select the **Target DB Home**
4. Click **Move Database**

📌 During move:
- Status = "Updating"
- If failed, reason is shown in the DB Home field

---

## 🔄 Upgrade Oracle Grid Infrastructure (GI)

Use the **OCI Console or APIs** to perform GI upgrades.

### 💡 Why Upgrade?
- Provision newer DB Homes and databases
- Stay current with Oracle database software

### 🔁 How GI Upgrade Works:

- Rolling fashion (1 node at a time)
- Monitor via **work requests**
- **Database instances on the node** being upgraded are unavailable

### ⚠️ Restrictions During GI Upgrade:

- No **Data Guard** operations
- No **provisioning**, **scaling**, **starting/stopping nodes**
- No **IORM edits**, **backups**, or **restores**

### 📌 Precheck is required:
- Not allowed if infrastructure maintenance is scheduled within 24 hours

---

## ⬆️ Upgrading the Database

### 🔐 Pre-Upgrade Tasks:

- Backup the database manually
- Test upgrade on non-prod system
- Create a new DB Home with the **target version**
- Ensure all **PDBs are open**
- Disable **automatic backups**

📌 After upgrading, **old backups can't be used** to restore the database to a pre-upgrade state.

---

## 🧭 Upgrade Process Summary:

1. Navigate to **Database Details Page**
2. Click **More Actions > Upgrade**
3. On the upgrade screen:
   - Select **Target DB version**
   - Select **Target DB Home**
4. Run **Precheck**
5. If passed, click **Upgrade Database**

### ⚠️ Special Consideration: Data Guard

- Upgrade **Standby first** is preferred
- Redo Apply will be **disabled during upgrade**
- After upgrade: verify **redo apply** and **open mode**

---

## 🏁 Summary of What You've Learned

By now, you should be able to:

✅ Create custom DB and Grid Infrastructure images  
✅ Create and manage DB Homes  
✅ Create and manage Databases and PDBs  
✅ Enable and configure Data Guard  
✅ Perform **patching** and **upgrades** for:
- Grid Infrastructure
- Database Homes
- Databases

---

🎉 **Thanks for following along!**  
Keep your Exadata Database Service secure, updated, and highly available by regularly performing user-managed maintenance and following Oracle’s best practices.

For deeper insights and hands-on labs, explore the [Oracle Cloud Infrastructure Docs](https://docs.oracle.com/en-us/iaas/).
