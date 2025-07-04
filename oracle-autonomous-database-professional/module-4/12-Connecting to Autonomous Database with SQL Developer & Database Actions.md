# 🧩 Connecting to Autonomous Database with SQL Developer & Database Actions

**Instructor:** Kamryn Vinson
**Topic:** Client and Web-based connection methods for ADB

---

## 🔐 Connect Using SQL Developer with **Cloud Wallet**

### 🪪 Prerequisites:

* Wallet file downloaded from ADB instance
* Username & password for the database user

### 🛠 Steps:

1. Open **SQL Developer**
2. Create a new connection:

   * Name: (Your choice)
   * Username & password: (e.g., `ADMIN`)
   * **Connection Type:** Cloud Wallet
3. Under **Configuration File**, select your downloaded wallet zip file
4. After selecting the wallet, choose a **Service** from the dropdown (e.g., *LOW*, *HIGH*, etc.)
5. Click **Connect**

📎 *Wallet contains the necessary configuration files and certificates for mutual TLS (mTLS) connection.*

---

## 🔓 Connect Using SQL Developer with **TLS (No Wallet)**

### ✅ Benefits:

* No wallet downloads or rotations
* Lower connection latency

### 🛠 Steps:

1. Open **ADB Details** → **Database Connection** tab
2. Copy the **TLS Authentication** connection string
3. Back in **SQL Developer**:

   * Connection Type: **Custom JDBC**
   * JDBC URL:

     ```
     jdbc:oracle:thin:@<tls_connection_string>
     ```
4. Enter username and password
5. Click **Connect**

🧠 *Requires proper TLS support (JDK 8+).*

---

## 🌐 Connect Using **Database Actions (SQL Developer Web)**

### 🚀 Launch:

* From your ADB instance page, click **Database Actions**

### 🧰 Features:

* SQL Worksheet
* Data Modeler
* REST API modules
* User Management
* Dashboard overview

### 🛠 SQL Interface:

* Create and run **SQL / PL/SQL**
* Create tables, triggers, insert & view data
* Features: Syntax highlighting, error messages, save results to files

---

## 👥 Grant Access to Others

### Option 1: UI Method

* Go to **User Management** in Database Actions
* Toggle **Web Access** to "On" for the user

### Option 2: SQL Method

```sql
BEGIN
  ords_admin.enable_schema('HR');
END;
/
```

This allows user `HR` to access Database Actions via the web interface.

---

## ✅ Summary

| Method                       | Wallet Needed | Tools  | Notes                               |
| ---------------------------- | ------------- | ------ | ----------------------------------- |
| SQL Developer (Cloud Wallet) | ✅ Yes         | GUI    | mTLS default secure method          |
| SQL Developer (TLS)          | ❌ No          | GUI    | Simpler setup, faster               |
| Database Actions             | ❌ No          | Web UI | In-browser SQL Dev with admin tools |

---

🎓 *You should now understand how to connect to your Autonomous Database using SQL Developer (with and without wallet) and Database Actions.*

📌 *Thanks for watching!*
