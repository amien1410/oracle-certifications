# 🛡 Oracle Data Safe

**Instructor:** Kamryn Vinson
**Topic:** Securing Oracle Cloud Databases with Data Safe

---

## 🔍 What is Oracle Data Safe?

Oracle Data Safe is a **unified control center** for managing and monitoring the security of your **Oracle databases**, both Autonomous and non-Autonomous. It helps with:

* 📊 Data sensitivity analysis
* 🔐 Security configuration assessment
* 👤 User risk analysis
* 🕵️ Activity auditing
* 🧪 Data masking
* ✅ Compliance with industry standards

**✅ Free service** included with Oracle Cloud databases
**💰 Charges** apply **only if audit records exceed 1M per month per target**
(Overage cost: \$0.08 per 10,000 records per target per month)

---

## 🧰 Key Features

| Feature                 | Description                                                                                   |
| ----------------------- | --------------------------------------------------------------------------------------------- |
| **Security Assessment** | Evaluates security of configs, user accounts, controls; recommends best-practice remediations |
| **User Assessment**     | Flags high-risk users based on authentication method, password age, and role privileges       |
| **Data Discovery**      | Finds sensitive data (PII, health, finance, etc.) by scanning tables and dictionaries         |
| **Data Masking**        | Replaces real sensitive data with realistic fake data for dev/test environments               |
| **Activity Auditing**   | Tracks database activity and alerts for unusual usage patterns                                |

---

## 🧱 Establishing a Security Baseline

* **Security Drift Detection**: Monitor for changes over time from a known-good state.
* **Privilege Cleanup**: Identify excessive user roles or unused privileges.
* **User Risk Baseline**: Define acceptable entitlement levels and monitor changes.

---

## 🧪 Data Masking Example Use Case

> ✅ You want to clone production data to a test environment
> ❌ Copying real user data would expose sensitive info
> ✅ Use Data Safe to **mask** data with fictitious values before copying

---

## 🛠 Enabling Oracle Data Safe

1. ✅ Go to your **Autonomous Database** (e.g., `ATPDEMO`)
2. 🔘 Click **Register** to enable Data Safe
3. 🖥 Click **View Console** to access the centralized dashboard
4. 🧭 From the dashboard, you can:

   * Run security and user assessments
   * Perform data discovery and masking
   * Monitor activity logs
   * Review compliance reports

🔄 To **stop using** Data Safe: click **Deregister**

---

## 🧩 Integration and Customization

* Comes with **predefined audit policies**
* Allows creation of **custom audit rules**
* Maps findings to **regulatory compliance frameworks**
* Supports **enterprise-wide deployment** for consistent security control

---

## 💡 Final Thoughts

* Most data breaches stem from **misconfigurations or compromised accounts**
* Oracle Data Safe helps you **detect, mitigate, and monitor** these risks
* Especially valuable in **non-prod environments** and for **regulatory compliance**

---
