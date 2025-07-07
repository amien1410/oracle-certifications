## 🔧 Patching & Upgrading Oracle Base Database Service

---

### ✅ Objectives

By the end of this guide, you will be able to:

- Understand best practices for updates and upgrades
- Locate and apply updates for:
  - Operating System (OS)
  - Grid Infrastructure (GI)
  - Database Home (DB Home)
- Perform upgrade of database versions (e.g. 12c → 19c)
- View patch history
- Use precheck and automation tools in the OCI Console

---

### 🧠 Best Practices Before Patching

- ☁️ **Back up the database** before any update
- 🛠️ **Patch DB system first**, then the database
- ✔️ Run **precheck** before applying patches
- 🟢 Ensure DB system and instances are healthy
- 💾 Ensure `/u01` has **at least 15GB** free
- 🔐 Use **Service Gateway** for object storage access
- 🔄 RAC patching is **rolling**, single-instance is not
- ⏱️ Schedule during **low-impact hours** due to reboots
- 👥 In Data Guard: **Update standby first**

---

### 🔄 Types of Updates

| Component            | Description                                 | Notes                                     |
|----------------------|---------------------------------------------|-------------------------------------------|
| **OS (VM)**          | Kernel and security updates                 | Applies to all systems                    |
| **Grid Infrastructure (GI)** | Oracle ASM, Clusterware, etc.          | Only for ASM-based or RAC systems         |
| **Database Home**    | Oracle DB patch versions (e.g., 19.21 → 19.22) | Use Oracle-provided or custom images      |

---

### 📋 Applying Updates via Console

1. **Navigate to DB System**
2. Click **View → Latest Patch Available**
3. Select from:
   - **Precheck** – Validate before patch
   - **Apply** – Runs precheck, then applies patch
4. Watch status:
   - “Applying” → Patch is in progress
   - “Applied” → Patch completed
5. For RAC: Each node is updated **one at a time**

---

### ⚙️ Updating Database Home

Options for patching or upgrading:
- 🏷️ **Oracle-Provided Images**
- 🧰 **Custom DB Software Images**

Steps:
1. Go to **Database Details** → View Patches
2. Choose patch from the available list
3. Select **Precheck** or **Apply**
4. Monitor progress and confirm success

---

### 🆙 Upgrading Database Version (e.g. 12c → 19c)

#### Preparation:
- 🔐 Back up the database
- 🧪 Test new version in dev environment
- ❌ Disable automatic backups temporarily
- ✔️ Run upgrade **Precheck**

#### Upgrade Steps:
- Sets **Guaranteed Restore Point (GRP)**
- Creates new **DB Home**
- Uses **DBUA** to run upgrade
- Removes GRP after successful upgrade

> ⚠️ If Data Guard is configured:
> - Upgrade **standby first**
> - Version 11.2/12.1: must disable DG before upgrade
> - GRP on standby must be manually removed

---

### 🗂️ Viewing Patch & Upgrade History

From **Database Details**:
1. Click **Update History**
2. View:
   - Precheck results
   - Applied patch/upgrade versions
   - Timestamps and statuses

---

### ⚠️ Notes on Upgrade to Oracle 19c

| Requirement                     | Status                      |
|--------------------------------|-----------------------------|
| Minimum OS Version             | Oracle Linux 7              |
| GI must be patched             | To 19c if using ASM         |
| Automatic backups              | Not usable after upgrade    |
| Upgrade downtime               | Required (not rolling)      |
| Can mitigate downtime via      | **Standby-first upgrade**   |

---

## 🎓 Summary

| Task                                      | Covered |
|-------------------------------------------|---------|
| Understand patching best practices        | ✔️      |
| Locate and apply OS, GI, DB patches       | ✔️      |
| Run prechecks and apply safely            | ✔️      |
| Upgrade DB version (e.g. 12c → 19c)       | ✔️      |
| Use console/API for patch operations      | ✔️      |
| View patch and upgrade history            | ✔️      |

> 🔄 Leverage Oracle’s cloud automation to safely update and upgrade systems with minimal risk and downtime.
