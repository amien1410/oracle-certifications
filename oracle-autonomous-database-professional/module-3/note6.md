# 🛠️ Autonomous Database Dedicated: Maintenance Scheduling

**Instructor:** Linda Foinding
**Course:** Oracle University's Autonomous Database Dedicated Infrastructure
**Topic:** Maintenance Control and Scheduling

---

## 📌 Overview

In Autonomous Database **Dedicated Infrastructure (ADB-D)**, customers gain **full control** over the **patching and maintenance schedule** for their databases, clusters, and infrastructure. Unlike serverless deployments, ADB-D offers **customizable, testable, and flexible** update options suited for enterprise needs.

---

## 🎯 Key Capabilities

| Feature                      | Description                                                                                                                |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Custom Scheduling**        | Choose which **month**, **week**, **day**, and **time window** in each quarter for updates.                                |
| **Independent Control**      | Separate patch schedules for: <br>• Exadata Infrastructure <br>• Autonomous VM Cluster <br>• Autonomous Container Database |
| **Environment Promotion**    | Promote patches from **development → staging → production** at your pace.                                                  |
| **Immediate Patch Option**   | Apply latest patch **immediately** if needed.                                                                              |
| **Skip Updates**             | Ability to **skip releases** and stay on a previous version until next cycle.                                              |
| **Dynamic Rescheduling**     | Reschedule specific patches if the default time isn’t convenient.                                                          |
| **Mission-Critical Support** | Assign different update strategies for critical workloads.                                                                 |

---

## 🧩 How It Works

* Oracle still **automates the patching**, but the **schedule and version control** is **in your hands**.
* ADB-D aligns with **enterprise best practices** by allowing:

  * Different patch levels for dev, staging, and production.
  * Transparent Application Continuity (TAC) to ensure patching has minimal user impact.
  * **One-off patches** to address urgent or specific customer needs outside regular cycles.

---

## 🛎️ Notifications and Events

Every quarter:

* **OCI Console** and **Notifications** alert administrators of new updates.
* Maintenance events include:

  * 📬 Schedule announcement
  * 🔔 Reminder
  * ▶️ Patch start
  * ✅ Patch end

---

## 🧠 Best Practices

* Patch **development** environments to the **latest version** regularly.
* Keep **staging and production** on validated, stable updates.
* Use **unique schedules** for mission-critical systems.
* Monitor updates via **OCI events and notifications**.

---

## ✅ Summary

Autonomous Database Dedicated offers:

* **Granular maintenance control**
* **Flexible patching**
* **Environment-specific update strategies**
* **Built-in Oracle best practices**

All while Oracle automates the heavy lifting behind the scenes.

---
