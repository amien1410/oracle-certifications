# 🧪 Managing Autonomous Database with OCI CLI

**Instructor:** Kamryn Vinson
**Lesson:** Oracle University – Using OCI CLI for Autonomous Database Management

---

## 🚀 What is OCI CLI?

The **OCI CLI** (Oracle Cloud Infrastructure Command Line Interface) is a lightweight tool for managing Oracle Cloud resources—Autonomous Databases included—**from the command line**.

### ✅ Key Benefits:

* Same core features as OCI Console
* Extra flexibility: automate scripts, schedule jobs, manage remotely
* Supports all major OS: **Mac, Windows, Linux**
* Based on **Python (v2.7.5, 3.5+)**

---

## 🔐 Prerequisites

To use the CLI:

1. An **OCI account** with user permissions
2. The **user must belong to a group** with necessary **policies**
3. A valid **API key pair**:

   * Public key uploaded to OCI Console
   * Private key kept securely by the user

> 💡 If Python is missing, the installer offers to auto-install it.

---

## ⚙️ Installation

### 🐍 Check Python version:

```bash
python --version
```

### 📦 Install OCI CLI:

```bash
bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
```

---

## 💻 Common OCI CLI Commands for ADB

Here are frequently used `oci db autonomous-database` commands:

| Command           | Description                                |
| ----------------- | ------------------------------------------ |
| `create`          | Provision a new Autonomous Database        |
| `delete`          | Delete an ADB instance                     |
| `get`             | Get details of an existing ADB             |
| `list`            | List all ADBs in a compartment             |
| `start` / `stop`  | Manage DB lifecycle                        |
| `update`          | Modify configuration (CPU, storage, etc.)  |
| `backup`          | Create, get, or list backups               |
| `restore`         | Restore from a backup                      |
| `generate-wallet` | Download wallet file for secure connection |

---

## 🛠️ Example: Create ADB via CLI

```bash
oci db autonomous-database create \
  --compartment-id ocid1.compartment.oc1... \
  --admin-password "YourDBadminPass123" \
  --db-name MyADB \
  --cpu-core-count 4 \
  --data-storage-size-in-tbs 1 \
  --display-name "CLI Demo ADB" \
  --db-workload DW \
  --license-model BRING_YOUR_OWN_LICENSE
```

> 🖥️ After running, check provisioning status via CLI or Console.

---

## 🧪 Additional Examples

### 🛑 Stop a database:

```bash
oci db autonomous-database stop --autonomous-database-id ocid1.autonomousdatabase.oc1...
```

### 🔁 Start it again:

```bash
oci db autonomous-database start --autonomous-database-id ocid1.autonomousdatabase.oc1...
```

### 🔁 List all ADBs:

```bash
oci db autonomous-database list --compartment-id ocid1.compartment.oc1...
```

---

## ✅ Summary

The OCI CLI gives you a **powerful, scriptable interface** to:

* Automate database lifecycle tasks
* Manage resources consistently
* Avoid GUI limitations
* Enable **DevOps** and **IaC workflows**

Great for DBAs, developers, and ops teams alike!

---
