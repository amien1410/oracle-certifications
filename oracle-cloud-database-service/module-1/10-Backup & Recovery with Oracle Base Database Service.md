## 🛡️ Backup & Recovery with Oracle Base Database Service

---

### 🗂️ Types of Backups

| Backup Type     | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| 🕒 **Automatic** | Scheduled by Oracle (Full weekly + Incremental daily). Redo logs backed up every 30 minutes. |
| 🧑‍💻 **On-Demand** | Manually triggered by user. Persist until manually deleted. |

Both types are encrypted by default and can be managed via **OCI Console** or **API**.

---

### 🏢 Backup Destinations

| Destination         | Features                                                                                     |
|---------------------|----------------------------------------------------------------------------------------------|
| 🪣 **Object Storage** | - Full + incremental backups<br>- Retention: 7–60 days (default 30)<br>- 7-day backup cycle |
| 🔐 **Recovery Service** | - Zero Data Loss Autonomous Recovery<br>- Immutable & replicated backups<br>- Real-time redo backup (every 30 mins)<br>- Retention: Up to **10 years** |

> 🔐 *Recovery Service* supports **incremental forever**, no need for weekly full backups.

---

### ⚙️ Configure Automatic Backups

You can **enable backups during or after DB creation**.

Steps (from Database Details page):
1. Click **Configure Automatic Backups**
2. Choose backup **destination**
3. Select:
   - 🔁 Retention policy
   - 🕓 Time window (initial + incremental)
   - ✅ Real-time protection (optional, extra cost)
4. Define behavior after **DB termination** (e.g. retain or purge after 72 hours)

---

### 🧭 View & Manage Backups

From the **Database Details → Backups** tab:
- See all automatic & on-demand backups
- Identify type from the column (e.g. “On-demand” or “Automatic”)

**Create On-Demand Backup:**
1. Click **Create Backup**
2. Name it
3. Click **Create** – status shows as *Creating*, then *Active*

---

### 🔄 Restore Options

You can restore a DB to:
- 🕒 **Latest state** – minimal data loss
- 📆 **Specific timestamp**
- 🔁 **System Change Number (SCN)** – for advanced recovery

From the **Database Details** page → click **Restore** and choose the mode.

---

### 🌍 Standby-Based Backup & Restore

If Data Guard is enabled:
- You can offload backups to the **standby DB**
- Restore the **primary DB** from **standby backup**, and vice versa
- Automate backup schedules on standby
- Create new DB systems from standby backups

⚠️ **Rules & Limits**:
- Backup destination must be the **same** for primary and standby
- If using Recovery Service, either DB can be restored from the other's backup
- If using Object Storage, each can **only** restore from its own backups

---

## ✅ Lesson Summary

| Capability                                | Supported? |
|-------------------------------------------|------------|
| Automatic and On-Demand Backups           | ✔️          |
| Backup to Object Storage and Recovery Svc | ✔️          |
| Configure backup retention & schedules    | ✔️          |
| Restore from latest, timestamp, or SCN    | ✔️          |
| Use standby DB for backup/restore         | ✔️          |
| View & manage all backups in UI           | ✔️          |

> ☁️ Oracle Cloud automation simplifies RMAN-based backup and restore—no scripting needed!
