# 🔔 Setting Up Service Notifications

**Instructor:** Kamryn Vinson
**Focus:** Managing announcements and notifications via OCI Console

---

## 🧭 Purpose of Notifications

Oracle Cloud **notifications** help keep administrators and users informed about:

* ✅ **Security alerts**
* 📊 **Quota breaches**
* ⚠️ **Planned/unplanned service outages**
* 📬 **Order approvals**
* 🛠 **Maintenance schedules**
* 🎁 **Promotions & updates**

Notifications are shown in the **Oracle Cloud Console**, and **visibility** depends on user **roles**:

| Role                          | What They See                                                        |
| ----------------------------- | -------------------------------------------------------------------- |
| Service Administrator         | Notifications for all services in current identity domain and region |
| Identity Domain Administrator | Notifications for all services globally                              |

---

## 🖥 Where to Manage Notifications

To access from OCI Console:

1. Go to **Governance and Administration > Announcements**
2. Or use the **shortcut on the top banner**

The **Announcements Page** displays:

* 🗓️ All **current and historical** notifications
* 📌 A new **dashboard** that categorizes key announcement types
* 🔎 Filters and sorting options for announcements

🔗 Includes a public **Oracle Cloud Infrastructure dashboard** for service status across regions.

---

## 📢 Setting Up Announcement Subscriptions

Oracle allows users to **subscribe to announcements** via OCI's **Notifications service**.

### What You’ll Need:

* A **Notification Topic** (where announcements are published)
* One or more **Subscriptions** (delivery endpoints like email, URL, Slack, SMS)

### Step-by-Step:

1. **Click**: Create Announcement Subscription

2. **Enter**:

   * Name
   * (Optional) Description
   * Compartment

3. **Select Subscription Type**:

   * 🟢 **All Announcements**
   * 🟡 **Selected Announcements Only** (filtered by criteria)

4. **Display Preferences**:

   * Set **Time Zone** for timestamps

5. **Create Notification Topic**:

   * Provide Compartment, Name, and optional Description

6. **Choose Subscription Protocol**:

   * Common options:

     * 📧 Email
     * 🔗 HTTPS or Custom URL
     * 📲 SMS
     * 🧠 Function
     * 🧵 Slack
     * ⏱ PagerDuty

7. (Optional) Add another subscription if needed.

8. ✅ **Click Create**

---

## 🎯 Summary

* Use the **Announcements page** to monitor system alerts and status.
* Subscribe to updates using **OCI Notification Topics**.
* Support for multiple delivery formats (email, SMS, webhooks, etc.)
* Helps administrators **proactively monitor and respond** to service issues or maintenance.

---
