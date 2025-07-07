## ⚙️ DB System Node Control & PDB Lifecycle Management

---

### 🧩 Node Operations (Start / Stop / Reboot)

To manage individual VM nodes of your DB system:

1. Go to your **DB System Details Page**
2. Under **Resources**, click **VM Nodes**
3. For each node, click **Actions (⋮)** to:
   - ▶️ **Start** – Restarts a stopped node
   - ⏹️ **Stop** – Gracefully powers off a node
   - 🔁 **Reboot** – Restarts the node

> 🧠 For **two-node RAC systems**, these actions must be done **individually** per node.

---

### 🗂️ PDB Management

🔹 Each DB System starts with:
- 1 **CDB** (Container DB)
- 1 **PDB** (Pluggable DB)

🔧 You can:
- ➕ **Create** additional PDBs
- 🔁 **Clone** PDBs (3 options):
  - **Local Clone** – Same CDB
  - **Remote Clone** – Different CDB
  - **Refreshable Clone** – Periodically synced

🔄 **Other Lifecycle Tasks** (via *More Actions*):
- ▶️ **Start / Stop**
- 🚚 **Relocate** to another DB system
- 💾 **Restore** to latest or specific point-in-time
- 🗑️ **Delete**

> 🧪 **Performance Hub** and **SQL Worksheet** tools available for PDB analysis and development.

---

### 💣 Terminating a DB System

❗ **Warning:** Termination **deletes** your DB system and all *incremental automatic backups*.

📝 **Backup First**: Perform a full on-demand backup if you want to keep your data.

💡 Key rules:
- You **cannot** terminate a **Primary DB** with an active Data Guard standby.
- Options:
  - 🔄 **Switch roles** (Primary ⟷ Standby), then terminate
  - ❌ **Delete standby first**, then terminate primary

🧭 Steps to Terminate:
1. Find DB system in console list
2. Click **Actions (⋮)** → **Terminate**
3. Confirm when prompted

🔴 System status will change to **Terminating**. All connections will close immediately.

---

## ✅ Lesson Summary

| Action                                      | Tools Available        |
|--------------------------------------------|------------------------|
| View DB System & DB Details                | ✔️ Console, API, CLI   |
| Scale OCPUs and Storage                    | ✔️ Console             |
| Create DB from Backup or PITR              | ✔️ Console             |
| Clone DB System or PDB                     | ✔️ Console             |
| Enable Data Guard                          | ✔️ Console, API        |
| Start / Stop / Reboot DB Node              | ✔️ Console             |
| Create / Manage / Clone / Restore PDB      | ✔️ Console             |
| Terminate DB System                        | ✔️ Console             |

> 🧠 Always review dependencies (e.g. Data Guard) before deletion or role changes.
