# 🛠️ Managing Autonomous Database Instances: Patching, Upgrades, and Services

**Instructor:** Kamryn Vinson
**Course:** Oracle University – Autonomous Database Dedicated Infrastructure

---

## 🔄 Maintenance, Patching & Upgrades

Autonomous Database **automates patching and maintenance** to ensure continuous availability.

### 🔧 Patch Levels

* **Regular**: Standard patching timeline
* **Early**: Patches applied **1 week earlier** than Regular

📝 **You must select patch level during provisioning or cloning**. It **cannot be changed** later.

| Action                      | Allowed? |
| --------------------------- | -------- |
| Clone Regular → Early       | ✅ Yes    |
| Clone Early → Regular       | ❌ No     |
| Change patch level directly | ❌ No     |

OCI Console shows the **next maintenance schedule** based on patch level.

---

## ⚙️ Database Services and Concurrency Management

Autonomous DB requires selecting a **service name** upon connection, which maps to a **consumer group**:

| Service    | Resources 🧠 | Concurrency 👥 | Execution |
| ---------- | ------------ | -------------- | --------- |
| `*_HIGH`   | Highest      | Lowest         | Parallel  |
| `*_MEDIUM` | Moderate     | Moderate       | Parallel  |
| `*_LOW`    | Lowest       | Highest        | Serial    |

### 🔢 Example: 16 OCPU Capacity

| Consumer Group | Concurrent Queries |
| -------------- | ------------------ |
| HIGH           | 3                  |
| MEDIUM         | 20                 |
| LOW            | 32–4800 (sessions) |

> ⚠️ When limits are reached:
>
> * `HIGH` and `MEDIUM`: new queries are **queued**
> * `LOW`: new **sessions are blocked**

---

## 🔁 Transparent Application Continuity (TAC)

Oracle hides maintenance, outages, and load shifts via **Transparent Application Continuity (TAC)** and **Application Continuity (AC)**.

### ✅ Key Concepts:

* **TAC**: Best for short, stateless transactions.
* **AC**: Maintains state and context like session duration, LOBs, etc.
* **Session Draining**: Active sessions are "drained" before patching.

Use **ORAchk Protection Reports** to verify levels of session continuity.

---

## 🧠 Advanced Concepts

| Term                   | Meaning                                                  |
| ---------------------- | -------------------------------------------------------- |
| **Mutables**           | Functions that return a **different value** on each call |
| **Request Boundaries** | Points where apps **borrow/return** DB connections       |

Exposing request boundaries enables:

* Seamless session restoration
* Load balancing
* Maintenance without breaking user experience

---

## 🧭 Summary

* Set patch level (Regular/Early) **only at provisioning**
* Use **consumer groups** to manage resource priorities
* HIGH = power, LOW = massive concurrency
* Use **TAC/AC** for uninterrupted applications during maintenance
* Enable **request boundaries** for session safety and resilience

---
