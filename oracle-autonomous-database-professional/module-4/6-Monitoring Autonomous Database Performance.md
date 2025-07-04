# 📊 Monitoring Autonomous Database Performance

**Instructor:** Kamryn Vinson
**Focus:** Metrics, Performance Hub, and Analytics Tools

---

## 📈 Where to Monitor Performance?

### ✅ **Metrics Resource Page** (in the DB Instance Details Page)

* Provides **current and historical metrics** for performance monitoring.
* Key metrics include:

| Metric              | Description                                                              |
| ------------------- | ------------------------------------------------------------------------ |
| **Storage**         | % of provisioned storage used (total for all tablespaces).               |
| **CPU Utilization** | % of CPU usage across all consumer groups (based on 2× number of ECPUs). |
| **Sessions**        | Number of active DB sessions.                                            |
| **Execute Count**   | Number of SQL statements executed (user + recursive) in the interval.    |
| **Running SQL**     | Number of currently executing SQL statements.                            |
| **Queued SQL**      | Number of SQL statements waiting to run (queued).                        |

📅 Use the **time selector** at the top of the chart to view custom date/time ranges (e.g., last hour).

---

## 🔍 **Performance Hub**

Accessible from the Autonomous Database details page, it offers **real-time and historical performance** views.

### Key Tabs in Performance Hub:

| Tab                   | Description                                                                 |
| --------------------- | --------------------------------------------------------------------------- |
| **ASH Analytics**     | View Active Session History, including wait events and bottlenecks.         |
| **SQL Monitoring**    | Monitor long-running and high-resource SQL statements.                      |
| **ADDM**              | Automatic Database Diagnostic Monitor report—deep insights & tuning advice. |
| **Workload**          | Summary of workloads by SQL, session, and time period.                      |
| **Blocking Sessions** | Identify and investigate blocking sessions causing performance issues.      |

📤 Exportable reports available via the **Reports dropdown**, such as **AWR (Automatic Workload Repository)** reports.

---

## 🛠 Use Cases

* Monitor for **storage thresholds** or spikes in **CPU usage**.
* Investigate **query bottlenecks**, session overload, or **SQL queuing**.
* Use ASH/ADDM to **troubleshoot application performance issues**.

---

## ✅ Summary

* The **Metrics page** helps track resource usage in near real-time.
* **Performance Hub** offers advanced diagnostic and historical analytics.
* Use this data to optimize queries, troubleshoot problems, and ensure high availability and performance.

---
