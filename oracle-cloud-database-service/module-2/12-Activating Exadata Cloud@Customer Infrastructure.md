# ⚙️ Activating Exadata Cloud@Customer Infrastructure

After provisioning your **Exadata Cloud@Customer (C@C)** infrastructure, the next crucial step is **activation**. Activation refers to the **physical setup and configuration** of the infrastructure in your on-premises data center. Let’s walk through the activation process step by step.

---

## 🚦 Pre-Activation: Check Infrastructure Status

- Navigate to your **Exadata Cloud@Customer Infrastructure** resource in the Oracle Cloud Console.
- Confirm that its status is: `**Requires Activation**`

---

## 📇 Add Primary Maintenance Contact

> ❗ **Required Step**

- Oracle needs a designated **Primary Contact** for activation-related communication.
- Go to **Infrastructure Details** page → Click **Manage Contacts**
- Add at least **one Primary Maintenance Contact**
- Activation **cannot proceed** without this contact

---

## 📁 Locate and Use the Activation File

- Oracle will provide you with an **activation file** after:
  - Hardware installation is completed
  - Initial base configuration is finished on-site

### 🔍 How to Use the Activation File:

1. On the **Infrastructure Details** page, click on the **“Show Guide”** link
2. This will expand a section that:
   - **Explains the steps** to perform activation
   - Allows you to **upload the activation file**

> 📝 This file is required to securely bind your infrastructure to the Oracle Cloud region and finalize provisioning.

---

## 🧠 Summary

| Step | Action |
|------|--------|
| ✅ Status Check | Confirm state is `Requires Activation` |
| 🧍 Add Contact | Add a **Primary Maintenance Contact** |
| 📂 Upload File | Use the **activation file** provided by Oracle |
| 📘 Show Guide | Follow on-screen instructions to complete activation |

Once these steps are complete, your **Exadata Cloud@Customer** infrastructure will be live and ready for further configuration, including VM cluster network creation and database provisioning.

➡️ Next: Creating the **VM Cluster Network** on Cloud@Customer.
