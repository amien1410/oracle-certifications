## 🔄 High Availability with Oracle Data Guard

---

### 🔐 What is Data Guard?

Oracle **Data Guard** ensures **high availability** and **disaster recovery** by maintaining a **synchronized standby** of your primary database.

| Term          | Meaning                                                                 |
|---------------|-------------------------------------------------------------------------|
| **Primary**   | Your main production database                                            |
| **Standby**   | A synchronized copy of the primary DB                                    |
| **Data Guard**| A configuration that includes both primary and one or more standby DBs  |

---

### 🎯 Key Capabilities

- 🔁 **Role switching** between primary and standby
- ⏱️ **Failover** during outages or disasters
- 🧪 **Point-in-time** recovery (PITR)
- 🧑‍💼 **Active Data Guard** (licensed) enables:
  - Read-only queries on standby (Real-Time Query)
  - Offloading backups
  - Snapshot standby, etc.

---

### 🧰 Protection Modes

| Mode                 | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **Maximum Performance** | ✅ Default. Fastest, asynchronous redo transfer. Possible data loss.       |
| **Maximum Availability** | ⚖️ Balance of data protection and uptime. Fallback to performance mode.   |
| **Maximum Protection**   | 🔐 Zero data loss. Transactions commit **only after** standby confirms redo is written. May halt DB on error. |

🔁 **Transport Modes**:

| Mode            | Wait for redo written to standby? | Speed     | Data Safety  |
|-----------------|-----------------------------------|-----------|--------------|
| `SYNC/AFFIRM`   | ✅ Yes                            | ❌ Slower | ✅ Safer      |
| `SYNC/NOAFFIRM` | ❌ No                             | ✅ Faster | ⚠️ Risky      |

---

### 🌐 Data Guard Deployment Options

| Option                  | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Intra-region**        | Primary & standby in **same VCN**, across **Availability Domains (ADs)**    |
| **Cross-region**        | Requires **Remote VCN Peering** between regions                             |
| **VCN Requirements**    | Security lists must allow **TCP ingress/egress** for DB ports               |

📍 *Examples*:

- 🔄 **Ashburn <--> Phoenix** = low-latency, intra-country
- 🌍 **Tokyo <--> London** = global DR setup (async only)

---

### 🚀 Enabling Data Guard in OCI Console

1. 🔎 Go to **DB System Details Page**
2. 📂 Select the **Database**
3. 🧭 In **Resources**, click **Data Guard Associations**
4. 🟢 Click **Enable Data Guard**
5. 🛠️ Enter required info for peer standby DB system

> This auto-creates a new DB system for the standby role.

---

### 🔃 Role Transitions

| Operation     | Use Case                      | Description                                                           |
|---------------|-------------------------------|------------------------------------------------------------------------|
| **Switchover**| 🔧 Planned maintenance         | Primary becomes standby, standby becomes primary                      |
| **Failover**  | ⚠️ Unplanned outage             | Promote standby to primary during catastrophic failure                |
| **Reinstate** | ♻️ Recover after failover       | Restore failed primary as standby after root cause is fixed           |
| **Fast Start Failover (FSFO)** | 🚀 Auto-failover     | Automatically promote standby during primary outage                   |

---

### 🧠 Summary Table

| Feature                     | Available?         |
|-----------------------------|--------------------|
| Data Guard in Standard Ed.  | ❌ No              |
| Data Guard in Enterprise Ed.| ✅ Yes             |
| Active Data Guard           | ✅ With license     |
| Manual PITR from backup     | ✅ Yes             |
| One standby per DB (UI/API) | ✅ Default support |
| Multiple standbys (manual)  | ✅ Advanced setup  |

---

💡 *“With Data Guard, your database is never truly alone.”*
