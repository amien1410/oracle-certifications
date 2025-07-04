# 🌐 Autonomous Database Connectivity

**Instructor:** Kamryn Vinson
**Topic:** Secure and Flexible Ways to Connect to Autonomous Database (ADB)

---

## 🔐 **mTLS (Mutual TLS) — Default Method**

* **Requires wallet download** (ZIP contains SSL wallet, keystore, truststore, etc.)
* **Both client & server authenticate each other**
* **Used by default** on ADB for **secure, encrypted communication**

🧳 **Client Credentials Wallet**

* Contains everything needed for secure connection
* Can be downloaded during provisioning

---

## 🔓 **TLS — Newer Option (No Wallet)**

* **No wallet needed** for JDBC Thin Driver (JDK8+) or SQL Developer
* **Reduced connection latency**
* **No wallet rotation maintenance**
* **mTLS + TLS** can coexist (choose based on client setup)

📌 *mTLS remains enabled by default.*

---

## 🧰 Supported Clients and Setup Overview

### ✅ JDBC (Java)

* **Version requirements**:

  * JDK 9+ required
  * Use `ojdbc11.jar` (v23.4+) or `ojdbc10.jar` (patch 19.30)
* **Configuration**:

  * Use `TNS_ADMIN` to point to wallet directory
  * Or set it inside JDBC URL directly

🧾 **Sample JDBC URL (with wallet)**

```
jdbc:oracle:thin:@db_high?TNS_ADMIN=/path/to/wallet
```

---

### 🖥 .NET Applications

* Options depend on deployment:

  * Visual Studio: Use Oracle Developer Tools & ODP.NET
  * NuGet: Use Package Manager for ODP.NET
  * Unmanaged ODAC: Download Oracle Data Access Components

⚙️ **Configuration**:

* Set wallet location in `sqlnet.ora`
* May need to enable TLS 1.3 on Windows

---

### 🌐 HTTP Proxy Support

* Add `https_proxy` and `https_proxy_port` in `tnsnames.ora`
* JDBC Thin driver 19.23+ is required

---

## 📁 Setting up the Wallet and Connection

1. **Download Wallet ZIP**
2. **Unzip to local directory**
3. **Set environment variable `TNS_ADMIN`** or point to path in connection string
4. **Configure `sqlnet.ora`**:

   ```ini
   WALLET_LOCATION = (SOURCE = (METHOD = file) (METHOD_DATA = (DIRECTORY=/wallet_path)))
   SSL_SERVER_DN_MATCH = yes
   ```

---

## 🧩 Sample Connection Methods

* **JDBC Thin URL**
  With `TNS_ADMIN` or inline path
* **Universal Connection Pool (UCP)**
  Similar setup using `ojdbc.properties` and wallet
* **Command Line (sqlplus, SQLcl)**
  Requires wallet
* **Scripting Languages (Python, node.js, etc.)**

  1. Install Oracle Instant Client
  2. Install language-specific drivers
  3. Use wallet & tnsnames.ora configuration

---

## 🛠 Developer Notes

* You can connect using various programming languages
* JDBC and scripting language support is well-documented
* Best practice is to manage connection configs securely and centrally

---

## 📌 Summary

| Method                     | Wallet Required | Notes                            |
| -------------------------- | --------------- | -------------------------------- |
| mTLS (default)             | ✅ Yes           | Secure mutual authentication     |
| TLS                        | ❌ No            | Easier setup, lower latency      |
| JDBC, SQLcl, SQL Developer | Depends         | Configure via wallet or TLS      |
| Python, node.js            | ✅ Yes           | Use Instant Client and TNS setup |

---
