# 🔐 Connecting to an Autonomous Database Using Wallet

**Instructor:** Cameron Vincent
**Topic:** Encryption, Wallet Configuration, Key Management, Secure Connection Setup

---

## 🔒 Encryption in Autonomous Database

* **Always-On Encryption** is enabled by default:

  * **Data at Rest** and **Data in Transit** are encrypted.
  * Encryption **cannot be disabled**.

* **Key Storage**:

  * Oracle manages master keys using a **secure PKCS12 keystore** located on Exadata systems.
  * Optionally, customers can use **Customer Managed Keys (CMK)**:

    * Control key **generation** and **rotation**.
    * CMKs are used automatically if the **Autonomous Container Database** is configured for it.

---

## 📎 Secure Connection Requirement

* Autonomous Database **only accepts secure connections**.
* To connect, you must **download a Wallet credentials file**:

  * Used in **SQL Developer**, **JDBC/ODBC apps**, and other tools.
  * Wallet file includes: TNSNAMES.ORA, SQLNET.ORA, certificate files, and keystore.

---

## 🧭 How to Download Wallet from the Console

1. **Locate Your Database** in the list on OCI Console.
2. Click the **three vertical dots (⋮)** → Choose **Service Console** or **DB Connection**.
3. In the **Connection popup**:

   * Choose **Instance Wallet** (1 database only) or **Regional Wallet** (all databases in the region).
4. **Enter a Wallet Password**.
5. Click **Download Wallet** to get a `.zip` file.

📌 *Store the credentials securely. Do not share with unauthorized users.*

---

## 🔄 Rotating Wallets (Key Rotation)

* Reasons: Compromised keys, periodic security policy, compliance.

### 🔁 Rotation Options:

| Option           | Effect                                          |
| ---------------- | ----------------------------------------------- |
| **Immediately**  | Old wallet is **instantly invalidated**         |
| **Grace Period** | Old wallet remains valid for **up to 24 hours** |

✅ *You must re-establish all connections using the **new wallet** after rotation.*

---

## 🧪 Demo Scenario Example

1. Chose to **rotate the wallet** with a **1-hour grace period**.
2. Downloaded the **new wallet**.
3. During the grace period, **both wallets** can be used to connect.
4. After the grace period, only the **new wallet** is valid.

---

## 📌 Summary

| Feature              | Description                                    |
| -------------------- | ---------------------------------------------- |
| **Encryption**       | Always-on (at rest & in transit)               |
| **Wallet Types**     | Instance or Regional                           |
| **Download Options** | Console (DB Connection) or API                 |
| **Key Rotation**     | Immediate or with grace period                 |
| **Customer Keys**    | Optional — provides control over key lifecycle |
| **Security Tip**     | Store wallets securely and limit access        |

---

🎓 *You should now understand how to securely connect to Oracle Autonomous Database using wallet-based credentials, including how to download, manage, and rotate them.*
