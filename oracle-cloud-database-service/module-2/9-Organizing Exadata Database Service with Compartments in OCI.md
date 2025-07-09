## 🗂️ Organizing Exadata Database Service with Compartments in OCI

In Oracle Cloud Infrastructure (OCI), **compartments** help organize cloud resources and control access using **Identity and Access Management (IAM)** policies. This is essential for maintaining security, operational clarity, and proper resource allocation within your organization.

---

### 🧩 What is a Compartment?

- A **compartment** is a **logical** grouping of resources, **not a physical container**.
- Only users/groups with explicit **IAM policies** can access/manage resources in a compartment.
- Used for:
  - Delegating management
  - Isolating environments (e.g., dev, test, prod)
  - Simplifying access control

---

### 🔁 What Resources Can Be Moved?

You can **move** the following Exadata resources between compartments:

| Resource Type             | Can Be Moved? | Notes |
|---------------------------|---------------|-------|
| ✅ Exadata Infrastructure | Yes           |       |
| ✅ VM Clusters             | Yes           | Dependent resources also move |
| ✅ Backup Destinations     | Yes           |       |

🧷 **Dependent resources** that move with VM Clusters:
- Database Homes
- Databases
- Automatic Backups

---

### 🛠️ How to Move Resources Between Compartments

Follow these steps:

1. **Navigate** to the `Exadata VM Cluster Details` page.
2. Under **More Actions**, click **"Move Resource"**.
3. On the **Move Resource** screen:
   - Select the **destination compartment**
   - Click **"Move Resource"** to complete

✅ **That’s it!** The cloud automation handles the migration smoothly.

---

### ⚠️ Permissions & Security Notes

- You **must** have **move permissions** on **both** the:
  - **Current compartment**
  - **Destination compartment**

- If the resource is in a **Security Zone**, the **destination compartment must also be a Security Zone**.

---

### 📚 What You’ve Learned in This Module

You should now be able to:

✅ Describe Exadata Database Service **management roles and responsibilities**  
✅ Understand and schedule **Oracle-managed infrastructure maintenance**  
✅ **Scale**:
  - Exadata Cloud Infrastructure
  - VM Clusters
  - VM Cluster Resources  
✅ **Move and manage** VM Clusters using compartments

---

### 🙏 Thank You!
Thanks for going through this module. You're now better equipped to manage and scale Oracle Exadata resources securely and efficiently in OCI.
