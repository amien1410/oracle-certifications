# 🌐 Configuring Disaster Recovery with Autonomous Data Guard

**Instructor:** Kamryn Vinson
**Topic:** High Availability, Data Guard, and Disaster Recovery in Oracle Autonomous Database

---

## 🔒 Built-In High Availability Features

Oracle Autonomous Database is delivered **highly available by default** with:

* **Oracle Real Application Clusters (RAC)**
* **Parallel Infrastructure**
* **Automated Backups**
* **Disaster Recovery**
* **99.95% SLA for uptime**

---

## 🧠 Why Enable Autonomous Data Guard?

* To achieve **higher SLA of 99.995%** (≈ **2 minutes of downtime per month**)
* Protects against:

  * **Planned downtime** (maintenance, patching)
  * **Unplanned downtime** (hardware failures, outages)
* Oracle guarantees **"no ridiculous exclusions"** in its SLA

---

## 🌍 Cross-Region Protection

* **Autonomous Data Guard (AuDG)** enables **cross-region standby databases**
* Oracle **optimizes inter-region connectivity** to ensure **fast switchover/failover**

---

## ⚙️ How to Enable Autonomous Data Guard

1. Go to **Database Console**
2. Click **Enable Autonomous Data Guard**
3. Choose:

   * **In-region** or **Cross-region** standby
   * Recovery type:

     * **Autonomous Data Guard** = fastest
     * **Backup-based recovery** = lower cost, slower

---

## 🔁 Technologies Behind the Scenes

| Technology                                   | Role                                                                             |
| -------------------------------------------- | -------------------------------------------------------------------------------- |
| **RAC** (Real Application Clusters)          | Horizontal scaling, handles local hardware/software failures                     |
| **ADG** (Active Data Guard)                  | Protects from **site-level disasters**, offers **standby replica** for reporting |
| **TAC** (Transparent Application Continuity) | Rebuilds session states automatically, masks failures from users/apps            |

> In **Dedicated Infrastructure**, all these are **autonomously managed** for **zero downtime experience**.

---

## 🧰 Features in AuDG on Dedicated Infrastructure

* **Autonomous Data Guard enabled at container creation**
* **Customer controls**: Switchover, failover, reinstate
* **Transport & Apply Lag metrics**
* **Symmetric standby actions**: Storage & compute mirrored
* **Clone database into AuDG container**
* **Read-only standby access**
* **Backups from primary and standby**
* **Protection modes**:

  * **Max Availability**
  * **Max Performance**

---

## 🔄 Active Data Guard Options

* Uses **physical replication** with **high isolation**
* **Synchronous & Asynchronous** protection supported
* **Automatic or Manual failover** based on RTO needs
* Enables **reporting** on standby database

---

## 📊 Availability and Performance Metrics

| Metric                 | Value                   |
| ---------------------- | ----------------------- |
| **SLA Uptime**         | 99.995%                 |
| **Max Downtime/Month** | \~2 minutes, 12 seconds |
| **App Impact**         | ≤ 30 seconds            |

---

## ✅ Summary

| Feature                      | Benefit                                    |
| ---------------------------- | ------------------------------------------ |
| **Autonomous Data Guard**    | Industry-best DR, simple enablement        |
| **Cross-region Standby**     | Geographic resilience                      |
| **RAC + ADG + TAC**          | Zero downtime + continuity                 |
| **Clone into AuDG**          | Easy migration to high-availability        |
| **Dedicated Infrastructure** | Self-operating high-availability framework |

---

🎓 *You should now understand how to enable and configure disaster recovery using Autonomous Data Guard for Oracle Autonomous Database.*
