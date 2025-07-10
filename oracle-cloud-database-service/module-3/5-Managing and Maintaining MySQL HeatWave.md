# 🛠️ Managing and Maintaining MySQL HeatWave on OCI

This section guides you through **management, monitoring, backups, performance, and maintenance** for your MySQL HeatWave Database System using the **OCI Console**.

---

## 📋 Database System Details Page

Accessible via OCI Console → **MySQL → Database Systems**

### 🔎 Sections:
- **Information Section**: Creation date, OCPUs, maintenance & backup windows
- **Resource Section**: FQDN, system status, HeatWave cluster info, replication channels
- **Connection Tab**: Private IP address of the DB system

---

## 🎯 Status Indicators

| Status     | Icon Color | Meaning                                          |
|------------|------------|--------------------------------------------------|
| Creating   | 🟡 Yellow   | Provisioning in progress                         |
| Active     | 🟢 Green    | Ready for use                                    |
| Updating   | 🟡 Yellow   | System is restarting or applying changes         |
| Inactive   | ⚪ Gray     | Stopped manually                                 |
| Deleting   | 🟡 Yellow   | In process of being deleted                      |
| Deleted    | ⚪ Gray     | Fully deleted                                    |
| Failed     | 🔴 Red      | Error occurred during creation or operation      |

---

## 🖲️ System Controls

Buttons available at the top of the Details page:

- **Start**: Resume a stopped system
- **Stop**: Halt system and stop billing for OCPUs (not for storage)
- **Restart**: Reboot the system
- **Edit**: Update name, description, shape, config, and maintenance window
- **Delete**: Permanently remove the system (requires confirmation)

---

## 🔧 Maintenance

- Occurs **automatically** during the defined window
- Includes patches to OS, MySQL Server, and hardware
- System becomes **temporarily unavailable** during updates
- If no window is set, OCI assigns one by default

---

## 📈 Monitoring & Metrics

Go to:  
OCI Console → MySQL DB Details → **Resources → Metrics**

### Track:
- 🧠 CPU, memory, and disk I/O
- 📡 Network activity
- 🧮 SQL statement performance and latency

Use **OCI Monitoring** to:
- Set **Alarms** on metrics
- Send **Notifications** (Email, PagerDuty, Slack, HTTPS, etc.)

---

## ⚙️ MySQL Configurations & Shapes

### 🔧 MySQL Configurations
- Define DB behavior using variables (like `my.cnf`)
- Default configs provided by OCI
- Can create **Custom Configurations** (not modify defaults)

### 🧩 OCI Shapes
Determine resources:
- OCPUs
- RAM
- Storage capacity

You can create and link custom configurations via:
`Databases → MySQL → Create Configuration`

---

## 🔐 Backups

OCI offers **two backup types**:

| Type        | Description                                     |
|-------------|-------------------------------------------------|
| 🔄 Full      | Backup of entire system                         |
| ➕ Incremental | Changes since the last full backup              |

### 🕹️ Backup Methods

- **Manual**:
  - Trigger via Console or API
  - Retain for 1–365 days
  - Limit: 100 per tenancy
- **Automatic**:
  - Scheduled within a defined window
  - Retain for 1–35 days (default: 7)
  - Cannot change retention after creation

To modify backup start time (e.g., from 12 AM → 4 AM):
- Go to **DB System Details → Edit Backup Configuration**

### 🔒 Required IAM Policies
To use backup features, assign:
- `mysql-backups`
- `mysql-instances`
- `mysql-work-requests`

---

## 🧘 Summary

✅ Understand MySQL HeatWave system status and controls  
✅ Schedule maintenance and monitor system performance  
✅ Track system health using metrics and notifications  
✅ Customize MySQL configurations and OCI shapes  
✅ Use and manage full & incremental backups for safety

Your MySQL HeatWave system is now **resilient, monitored, and ready to scale** 🚀
