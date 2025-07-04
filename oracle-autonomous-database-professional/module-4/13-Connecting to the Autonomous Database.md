# 🌐 Connecting to the Autonomous Database

**Instructor:** Kamryn Vinson
**Topic:** Connection methods, service levels, wallets, and security

---

## 🔌 Database Connection Services

Each **TNS service** in the wallet provides different performance & concurrency characteristics:

| **Service Name** | **Use Case**           | **Priority** | **Parallelism**                        |
| ---------------- | ---------------------- | ------------ | -------------------------------------- |
| `tpurgent`       | Time-critical OLTP     | Highest      | ✅ Manual parallelism                   |
| `tp`             | Standard OLTP          | High         | ❌ No parallelism                       |
| `high`           | Reporting / Batch      | High         | ✅ Full parallelism, subject to queuing |
| `medium`         | General Reporting      | Medium       | ✅ Limited parallelism (up to 4 DOP)    |
| `low`            | Low-priority reporting | Low          | ❌ No parallelism                       |

📌 *Sessions idle for 5+ minutes may be disconnected to free up resources.*

---

## 🔐 Wallet Types

| **Wallet Type**          | **Scope**            | **Use Case**                            |
| ------------------------ | -------------------- | --------------------------------------- |
| **Instance Wallet**      | 1 DB only            | Autonomous DB Serverless, general users |
| **Regional Wallet**      | All ADBs in a region | DBA use only (multi-instance access)    |
| **Dedicated ADB Wallet** | 1 DB only            | Autonomous DB Dedicated                 |

🎯 The **TNSNAMES.ORA** file in the wallet contains all necessary service entries.

---

## 🧠 Supported Connection Methods

| Method          | Description                                 | Notes                         |
| --------------- | ------------------------------------------- | ----------------------------- |
| **SQL Net**     | Traditional Oracle client access            | Requires wallet or TLS config |
| **JDBC (Thin)** | Java apps use Thin Driver                   | Use JKS or wallet credentials |
| **ODBC**        | For BI/reporting tools like Excel, Power BI | Needs Oracle Instant Client   |
| **Data Pump**   | For data import/export                      | Uses Oracle client calls      |

---

## 🔐 Authentication Options

* **With Wallet (mTLS):**

  * Default & secure method using SSL/TLS mutual authentication
  * Requires wallet download

* **Without Wallet (TLS-only):**

  * Lower latency, no wallet management
  * Works with tools like SQL Developer, JDBC (JDK 8+)

---

## 🔑 Using API Keys for Scripted Access

* Generate a **key pair**
* Upload **public key** in OCI Console:
  `Identity > Users > Add Public Key`
* Use **private key** in CLI or API scripts

---

## 🌍 Connectivity Options

### 1. **Public Internet (SSL)**

* Simplest method
* Requires opening **port 1522** on firewall
* Wallet or TLS auth required

### 2. **FastConnect (Public Peering)**

* Private connectivity to Oracle Cloud
* SSL still used
* Offers enhanced security, lower latency

### 3. **Service Gateway (Private Access)**

* No traffic over public internet
* Complete **network isolation**
* Ideal for high-security environments

---

## ✅ Summary

| Feature                  | Notes                                         |
| ------------------------ | --------------------------------------------- |
| **Wallet Types**         | Instance, Regional (DBA only), Dedicated      |
| **Connection Types**     | SQLNet, JDBC, ODBC, Data Pump                 |
| **Authentication**       | mTLS (default), TLS (no wallet)               |
| **Services**             | tpurgent, tp, high, medium, low               |
| **Connectivity Options** | Public internet, FastConnect, Service Gateway |
| **Port to Open**         | `1522`                                        |

---

🎓 *You now understand how to securely connect to Oracle Autonomous Database using various clients, services, and wallet configurations.*
