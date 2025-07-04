# 🔐 Managing Encryption Keys in Oracle Autonomous Database

**Instructor:** Kamryn Vinson
**Lesson Topic:** Transparent Data Encryption (TDE) & Key Management

---

## 🧾 What is Transparent Data Encryption (TDE)?

TDE encrypts sensitive data **at rest**, helping protect it even if the storage medium or data file is stolen.

* ✅ **Encryption is automatic and transparent** to authorized users/apps.
* 🔐 **Data files** are protected even when the OS or database is compromised.
* 🔍 Complements Oracle DB’s existing **authentication**, **authorization**, and **auditing**.

---

## 🔐 How Does TDE Work?

* Data is **encrypted at the file level**, not just in the DB.
* Encryption keys are **stored outside** the database in a **keystore**.
* You can configure **Oracle Key Vault (OKV)** to:

  * Manage TDE keystores centrally
  * Share keys across multiple TDE-enabled databases

---

## ☁️ Encryption in Oracle Autonomous Database

Oracle Autonomous Database provides **"Always-On" Encryption**:

| Area                 | Encryption Type             | Description                                             |
| -------------------- | --------------------------- | ------------------------------------------------------- |
| Data at Rest         | Transparent Data Encryption | Files stored on disk are encrypted                      |
| Data in Transit      | Transport Layer Security    | Data moving across networks is protected                |
| Admin Access Control | Database Vault              | Prevents privileged users from unauthorized data access |

---

## 🔐 Master Encryption Keys

| Option                    | Description                                                           |
| ------------------------- | --------------------------------------------------------------------- |
| **Oracle-managed keys**   | Default option; keys stored in a secure PKCS12 keystore on Exadata    |
| **Customer-managed keys** | Optional; allows companies to control key **generation and rotation** |

> 🔁 **Customer-managed keys** are automatically used if the Autonomous Container Database (ACD) is configured for them.

---

## 📦 End-to-End Encryption Layers

```
[ Application Layer ]
        ↓ (TLS)
[ Network Layer - Encrypted in Transit ]
        ↓
[ Autonomous Database ]
        ↓ (TDE)
[ Storage Layer - Encrypted at Rest ]
```

---

## ✅ Summary

* Oracle Autonomous DB **encrypts everything** by default—no opt-out.
* TDE secures **data files** while TLS secures **data in motion**.
* Customers can use **Oracle-managed** or **customer-managed** encryption keys.
* Centralized management possible with **Oracle Key Vault**.
* **Database Vault** prevents privileged users from snooping on protected data.

---
