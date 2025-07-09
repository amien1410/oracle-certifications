# 🔧 User-Managed Maintenance in Exadata Database Service

In this section, we explore **user-managed maintenance responsibilities**, best practices, and how to manage **patching and updates** for your Exadata Database Service infrastructure, especially the VM Cluster and Database Homes.

---

## 🛠️ Maintenance Responsibility Matrix

Maintenance tasks are divided into two categories:

### 1. **Oracle-Managed Maintenance**
Oracle is responsible for:
- Quarterly updates to infrastructure components:
  - Compute servers, root VMs
  - Exadata storage servers
  - RDMA network (RoCE switches)
  - PDUs, ILOMs, firmware
  - Control plane components

This is referred to as **infrastructure maintenance**.

---

### 2. **User-Managed Maintenance**
You are responsible for:
- Updating Oracle **Grid Infrastructure**
- Patching Oracle **Database software**
- Updating the **Operating System** (OS) on VM nodes

🔁 These should be done **quarterly**, not exceeding **180 days** between patches.

---

## 🛡️ Access Control

- Ensure your user is granted appropriate **IAM policies** for patching and maintenance.
- If you receive "unauthorized" messages, contact your **tenancy administrator**.

---

## ✅ Best Practices for Maintenance

| Task | Recommendation |
|------|----------------|
| 🗄️ Backup | Always **backup** the database before patching |
| 🏗️ Database Homes | Prefer creating a **new Database Home** over updating existing ones |
| ⚙️ Grid Infrastructure | Patch **Grid Infrastructure first** before Database Homes |
| ✅ Pre-check | Run **pre-checks** ahead of your maintenance window |
| 💾 Free Space | Ensure: <br> `/u01` ≥ 15 GB (Grid Infra) <br> `/u02` ≥ 15 GB (Database Home) |
| 🧭 Tools | Use **OCI Console, REST API, or CLI** for updates |

---

## 🔍 Viewing Patch Levels and Updates

1. Go to your **VM Cluster Details** page.
2. In the **Version** section:
   - View current **Exadata image** and **Grid Infrastructure** patch levels
3. In the **Database** section:
   - View Database Home versions for each DB

👉 Click **View Updates** to access available patches.

---

## 📑 The Updates Page

Organized into three sections:

### 1. **Exadata VM Cluster OS Updates**
- Includes guest VM OS updates (Exadata image)
- Fields:
  - Description
  - Version
  - Release Date
  - Last Precheck Timestamp

### 2. **Grid Infrastructure Updates**
- Includes patches/upgrades
- Similar fields as above + **Type** (Patch/Upgrade)

### 3. **Database Home Updates**
- Oracle-provided and custom images
- Fields:
  - Description
  - Version
  - Release Date
- Use **scope selector** to filter patches by Database Home

---

## 🕓 Update History

Use the **Update History** page to:
- View patch operations (Prechecks & Apply)
- See timestamps and statuses (Success/Failure)
- Retry failed operations

❗ Note: Console history does **not** show patches applied via `dbcli` or CLI tools.

---

## ⬆️ Updating Guest VM OS (Exadata Image)

- Performed via **OCI Console or REST APIs**
- Simplifies and automates VM OS patching
- Eliminates need for manual `patchmgr`

### 📝 Steps:

1. Go to **Updates Page**
2. Choose desired **OS update version**
3. Click **Run Precheck**
   - Validates readiness
4. If passed, click **Apply Exadata OS Image Update**
5. Confirm:
   - VM Cluster name
   - Target OS version

Oracle only provides the **four latest** Exadata image minor versions in the console.

---

## 🚦 Final Notes

- Prechecking before applying updates is **critical**
- Use **OCI UI or API** for best experience
- Follow patching cadence every 3–6 months to maintain system health and security

---
