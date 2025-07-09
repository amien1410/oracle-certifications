# 🔄 Exadata Database Service: PDB Management & Data Guard

This section expands on lifecycle operations for **Pluggable Databases (PDBs)** and implementing **Oracle Data Guard** for high availability and disaster recovery.

---

## 🧩 Pluggable Database (PDB) Management

### ➕ Creating a New PDB
1. Go to **Database Details**
2. Click **Create Pluggable Database**
3. Enter:
   - PDB name  
   - Admin password
4. Click **Create Pluggable Database**

The new PDB will appear in the list of available PDBs.

---

### 🔌 Connecting to a PDB
- Use **Easy Connect** or **Long Connect** strings
- Access performance metrics via **Performance Hub**

---

### 🔁 Cloning a PDB

1. Go to the **Pluggable Database Details**
2. Click the **Clone** tab
3. Choose one of the following clone types:
   - **Local Clone**: Within same Container Database (CDB)
   - **Remote Clone**: Different CDB, same availability domain
   - **Refreshable Clone**: Remote PDB that supports periodic refreshes
4. Configure:
   - Destination CDB  
   - Clone PDB name & admin credentials
5. Click **Clone Pluggable Database**

---

### ⚙️ More PDB Lifecycle Actions

Under the **More Actions** tab:

- 🟢 **Start/Stop** a PDB
- 🔁 **Relocate** PDB to another DB system
  - Input: Destination DB system, new name/password (optional)
- ♻️ **Restore** a PDB
  - Choose latest backup or specific point-in-time
- 🗑️ **Delete** a PDB
  - Confirm via dialog box

---

## 🛡️ Enabling Oracle Data Guard

Data Guard provides **real-time disaster recovery** by maintaining standby databases.

### 💡 Benefits
- Real-time sync between primary & standby
- Supports:
  - Planned switchover (maintenance)
  - Unplanned failover (disaster)
  - Manual or automatic failover (FSFO)
- Minimal downtime during maintenance

---

### 🚀 Enabling Data Guard

1. From Console, select the **peer VM cluster** for standby
2. Choose **Data Guard type**:
   - **Data Guard**
   - **Active Data Guard** (supports read-only queries and faster backups)
3. Select:
   - Use existing or create new Database Home
   - Input unique name for standby DB
   - Input standby admin password (must match primary)
4. Click **Enable Data Guard**

---

### 🔁 Data Guard Role Transitions

- **Switchover**: Planned transition (e.g., patching)
- **Failover**: Unplanned due to failure
- **Reinstate**: Bring failed primary back as standby
- **Fast Start Failover (FSFO)**: Automatic failover to a selected standby

---

## ⚠️ Data Guard Requirements

| Requirement                             | Details                                                                 |
|----------------------------------------|-------------------------------------------------------------------------|
| Same Compartment                       | Both DB systems must be in same compartment                            |
| Same VCN (if same region)              | Or use **VCN peering** if in different regions                         |
| Same Database Version                  | Must be identical                                                       |
| Unique DB Unique Name                  | Required for each database in the association                          |
| Security Rules                         | Ingress/egress TCP (port `1521` SCAN listener); ensure rules are stateful |

---

## ✅ Summary

With Exadata Database Service, you can:

- Manage **Pluggable Databases**: create, clone, relocate, restore, delete
- Use **custom lifecycle operations** from Console or API
- Enable **Oracle Data Guard** with minimal steps for full DR protection
- Support **planned/unplanned failovers** and high availability architecture
