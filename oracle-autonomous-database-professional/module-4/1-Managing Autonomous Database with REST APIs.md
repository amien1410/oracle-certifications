# 📡 Managing Autonomous Database with REST APIs

**Instructor:** Kamryn Vinson
**Lesson:** Oracle University – Using REST APIs for ADB Management

---

## 🚀 Overview

Oracle Cloud Infrastructure (OCI) provides **REST APIs** to manage Autonomous Databases (ADB), allowing **DBAs and developers** to automate operations, standardize deployments, and version-control their infrastructure—**without relying on the Console UI**.

---

## 🧰 Why Use REST APIs?

* Avoid manual UI-based operations.
* Build reusable scripts for:

  * Provisioning
  * Scaling
  * Starting/Stopping
  * Backup/Restore
* Store infrastructure as **code**.
* Adopt **DevOps** and **IaC (Infrastructure as Code)** best practices.

---

## 🔐 Security & Standards

* All REST API requests use:

  * **HTTPS** protocol
  * **TLS 1.2** encryption
  * **Signed requests** (no username/password)
* Signing follows `draft-cavage-http-signatures-08` spec.
* Authentication requires:

  * **Private key** in PEM format
  * **RSA-SHA256** signature algorithm

---

## 🧾 How to Make a REST API Call

### 📝 Step-by-step

1. **Form HTTPS request**
2. **Create a signing string** (includes request details)
3. **Sign** it using RSA-SHA256 + your private key
4. **Add Authorization header** with the signature
5. **Send the request** (e.g. using `curl`, `Python`, `Node.js`, etc.)

> 💡 Tip: Use SDKs or CLI if you want abstractions for authentication and signing.

---

## 📦 Common API Operations

| Operation        | Endpoint Example                           | Description                                          |
| ---------------- | ------------------------------------------ | ---------------------------------------------------- |
| `CREATE`         | `/autonomousDatabases/`                    | Provision a new ADB with CPUs, storage, and password |
| `DELETE`         | `/autonomousDatabases/{id}`                | Delete an existing ADB                               |
| `START` / `STOP` | `/autonomousDatabases/{id}/actions/start`  | Manage database lifecycle                            |
| `SCALE`          | `/autonomousDatabases/{id}` + payload      | Resize CPUs/storage                                  |
| `BACKUP`         | `/autonomousDatabases/{id}/actions/backup` | Initiate on-demand backup                            |

> ✅ All responses return **JSON** with ADB metadata: status, CPU count, storage, creation time, links, and more.

---

## 🛠️ Supported Languages

You can integrate OCI REST APIs into scripts written in:

* Python
* Node.js
* Java
* Bash
* Curl
* Ruby
* Perl

---

## 🧪 Example: Creating an Autonomous Database

```bash
curl -X POST https://.../autonomousDatabases/ \
  -H "Authorization: Signature ..." \
  -d '{
    "compartmentId": "...",
    "dbName": "adatabasedb1",
    "cpuCoreCount": 8,
    "dataStorageSizeInTBs": 1,
    "adminPassword": "...",
    "displayName": "ADB REST Created"
  }'
```

Response includes:

* `status`: e.g., `PROVISIONING`
* `cpuCoreCount`: 8
* `dataStorageSizeInTBs`: 1
* `timeCreated`: timestamp
* `consoleUrl`: direct UI link

---

## ✅ Summary

Using REST APIs to manage your Autonomous Database offers:

* **Flexibility** for automation
* **Security** with signed requests
* **Portability** across environments
* **DevOps-readiness** with repeatable scripts

Perfect for developers, DBAs, and platform engineers building modern, cloud-native apps.

---
