# 📘 Oracle Base Database Service – Provisioning, Networking, IAM & Access

👨‍💻 *Module 3: Provisioning the DB System + Understanding OCI Networking & IAM*

---

## 🚀 What You'll Learn

After this module, you should be able to:

- Understand **OCI networking** and **IAM** concepts
- Identify **prerequisites** to launch a Base Database Service
- Provision a **DB system using the OCI Console**
- Configure **networking, compute, storage, and licensing**
- Use and manage **resource tags**
- Understand **pre-configured OS users**
- **Connect via SSH** to your VM DB system

---

## 🌐 OCI Networking Fundamentals

### 🔸 Virtual Cloud Network (VCN)
- A **software-defined network** with:
  - **CIDR block**
  - **Subnets** (regional or AD-specific)
  - **Route Tables & Security Lists**
- VCNs support public and private subnets.

### 🔸 Gateways
- Enable traffic between VCN and external services:
  - **Internet Gateway** (for public access)
  - **Service Gateway** (private access to OCI services)
  - **Dynamic Routing Gateway (DRG)** – for on-prem connectivity (VPN/IPSec/FastConnect)

---

## 👥 OCI Identity & Access Management (IAM)

IAM controls **who** can access **what** and **how**.

### Key IAM Concepts:
| Term         | Description |
|--------------|-------------|
| **Principals** | Entities (users, groups) that request access |
| **Users**      | Individuals or services accessing OCI |
| **Groups**     | Collections of users with the same permissions |
| **Policies**   | Rules that define who can do what |
| **Compartments** | Logical containers for OCI resources |

### 🧾 Example IAM Policy

```text
Allow group DBA_Admins to manage database-family in tenancy
````

This policy gives the `DBA_Admins` group full control over all database-related resources.

> ✅ DB Systems can be moved across compartments with proper permissions

---

## 📋 Prerequisites for Provisioning a DB System

To launch a VM-based DB system, ensure:

* ✅ **IAM policies** are correctly configured
* ✅ **VCN & subnet** (preferably private) are ready
* ✅ **OpenSSH public key** is provided (for VM access)
* ✅ **Port 22 open** (for SSH – required for both ingress and egress)
* ✅ **Internet Gateway or Service Gateway** is available for backups

---

## 🖥️ Launching a Base DB System via Console

1. **Sign in** at [cloud.oracle.com](https://cloud.oracle.com)
2. **Navigate** to:

   * **Menu → Oracle Database → Oracle Base Database Service**
3. **Click** `Create DB System` and follow steps:

### 🛠 Configuration Steps

* Set name, compartment, and availability domain
* Select:

  * **VM shape** (Ampere, AMD, or Intel)
  * **OCPUs and storage**
  * **License model**
* Provide:

  * **SSH keys**
  * **VCN and subnet**
  * **Hostname and database names**
  * **Admin password**
* Enable:

  * **Automatic backups**
  * **Storage management software (ASM or LVM)**

✅ Once created, check the **DB System State**:
`Provisioning → Available → Updating → Stopped → Terminated`

---

## 🏷️ Resource Tagging

Tags help organize and manage resources:

### Tag Types

| Tag Type          | Who Can Use It                    |
| ----------------- | --------------------------------- |
| **Defined Tag**   | Admin-created, role-restricted    |
| **Free-form Tag** | Any user with resource permission |

Use tags to:

* Group and track resources
* Automate billing or reporting
* Apply bulk actions (e.g., cleanup, updates)

---

## 👤 DB System OS User Accounts

| User     | Purpose                      | Access Method      |
| -------- | ---------------------------- | ------------------ |
| `opc`    | Entry point, use with `sudo` | SSH (public key)   |
| `oracle` | DB admin                     | `sudo su - oracle` |
| `root`   | System admin                 | `sudo su - root`   |
| `grid`   | Grid Infra admin (ASM only)  | `sudo su - grid`   |

> ℹ️ `grid` user **not available** for single-node systems using **LVM**

---

## 🔐 SSH Access to DB System

### Requirements:

* SSH **private key** matches the **public key** provided during provisioning
* **Port 22** must be open for SSH traffic

### Steps:

```bash
ssh -i ~/.ssh/my_key.pem opc@<public_ip_address>
```

Then:

```bash
sudo su - oracle    # for DB tasks
sudo su - root      # for system tasks
sudo su - grid      # for ASM/Grid tasks (if applicable)
```

> ❗ Validate firewall rules if you encounter SSH connection issues

---

## ✅ Summary

* VCNs and IAM policies are essential for secure provisioning.
* OCI Console simplifies DB System setup.
* Use tags and compartments for resource management.
* Securely connect and manage DB VMs via SSH and predefined users.

---

🧑‍🎓 *You now have the hands-on knowledge to provision and access your Oracle Base Database Service on OCI. Build smart, secure, and scalable cloud databases like a pro!*
