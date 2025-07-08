## 🔧 Oracle Exadata Infrastructure Maintenance

---

### 🎯 Learning Objectives

After completing this section, you will be able to:

- Understand Oracle's regular infrastructure patching and update cycles
- Differentiate between infrastructure and user-managed maintenance
- Configure and reschedule infrastructure maintenance windows
- Review maintenance history and interpret scheduling preferences

---

### 🗓️ Exadata Maintenance Overview

Oracle performs **regular infrastructure maintenance** to ensure:

- Platform **security**
- Performance and **reliability**
- Deployment of **new features**

🛠️ **Types of Maintenance**:
1. **Quarterly Bundle Patches** (rolling updates, default)
   - Infrastructure patches
   - OS & cloud software updates
   - Exadata image updates
2. **Exadata Software Releases**
   - New features and hardware support
3. **Time-Sensitive Critical Patches**
   - Applied within 21 days for CVSS > 7
   - Automatic online patching with **Ksplice** for public cloud

---

### 🔁 Rolling vs. Non-Rolling Maintenance

| Mode        | Description | Impact |
|-------------|-------------|--------|
| **Rolling** | One server updated at a time | Minimal downtime |
| **Non-Rolling** | All components patched at once | Full outage required |

🔄 **Default**: Oracle applies patches **in a rolling fashion** to maintain availability.  
🧠 **ASM High Redundancy** protects data across 3 storage servers, ensuring continued DB access during storage server maintenance.

---

### 🔐 Monthly Critical Security Updates

- Applied automatically (public cloud) or within a **21-day reschedulable window** (Cloud@Customer)
- Delivered with advanced notice (typically **2 weeks**)
- ⚠️ Notification if updates affect DB server VMs

---

### 🧭 Infrastructure Maintenance Preferences

From the **Exadata Infrastructure Details** page, you can:

1. **Click:** `Edit Maintenance Preferences`
2. **Select:**
   - `Rolling` or `Non-Rolling`
   - Maintenance **months per quarter**
   - Week of the month (starts: 1st, 8th, 15th, 22nd)
   - Day of the week (or leave blank for default)
   - Start hour (or leave blank for least disruptive time)
   - Notification lead time (e.g. 2 or 4 weeks)

📝 Oracle honors your defined window or applies default if none is set.  
🔁 Customers can reschedule maintenance up to **180 days** from last maintenance.

---

### 📅 Managing Maintenance Schedule

From the same Exadata Infrastructure panel:

- **View** upcoming scheduled maintenance
- **Click:** `Edit Maintenance Run` to change date/time
- Review:
  - Maintenance method
  - Start time
  - Estimated duration

### 🧾 Maintenance History View

To audit past maintenance:

- Click **Maintenance History**
- See:
  - Dates and duration of prior maintenance events
  - Type of patch applied (OS, Exadata image, etc.)
  - Method (Rolling/Non-Rolling)

---

### ✅ Summary

| Key Topic                        | Covered |
|----------------------------------|---------|
| Quarterly and critical updates   | ✔️      |
| Rolling vs. non-rolling patching | ✔️      |
| Security patch timelines         | ✔️      |
| Maintenance schedule preferences | ✔️      |
| Maintenance history audit        | ✔️      |

Oracle ensures infrastructure **security**, **availability**, and **compliance** with industry standards while giving you tools to control **timing** and **visibility** of updates. With rolling patching and ASM redundancy, the Exadata platform ensures **minimal disruption** to mission-critical workloads.
