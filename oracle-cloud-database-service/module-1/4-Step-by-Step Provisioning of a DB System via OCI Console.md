# 🧪 Oracle Base Database Service – Guided Provisioning Demo (Console)

👨‍🏫 *Module 4: Step-by-Step Provisioning of a DB System via OCI Console*

---

## 🧭 Overview

This walkthrough reflects the **Oracle-recommended provisioning workflow** for setting up a **Base Database Service DB System** via the **OCI Console**. This process grants granular control over database system configuration, compute architecture, licensing, storage performance, and network architecture—ensuring enterprise-grade flexibility and availability.

---

## 🔧 Step-by-Step DB System Provisioning

### 1. 🧭 Navigate to the Base DB Service Console

- Access: **OCI Console → Oracle Database → Oracle Base Database Service**
- Action: Click **`Create DB System`**

---

### 2. 📝 Fill in DB System Configuration

#### 🔹 General Information
- **Name**: Provide a meaningful system identifier.
- **Availability Domain (AD)**: Choose the AD to localize your system for fault isolation.

#### 🖥️ VM Shape Configuration
- **Processor Type**: Choose between **Ampere, AMD, or Intel**
- **OCPUs**: Use the slider to allocate OCPUs per node
- **Compute Nodes**: 1 for single-instance or 2 for RAC

#### 💾 Storage Settings
- **Storage Mgmt Software**: Select:
  - `Oracle Grid Infrastructure` (for ASM-based setups)
  - `Logical Volume Manager` (for simplified single-node provisioning)
- **Performance Level**: Choose based on IOPS/throughput needs
- **Storage Size**: Define volume size (scalable later)

#### 🔑 Access & Licensing
- **SSH Key**: Upload public key to enable secure SSH login
- **License Type**:
  - `License Included` – Includes Oracle DB licenses
  - `Bring Your Own License (BYOL)` – For cost optimization with existing entitlements

#### 🌐 Network Setup
- **VCN & Subnet**: Choose from pre-configured networks
- **Hostname Prefix**: Set for system DNS
- **Enable Diagnostics**: Recommended for enhanced troubleshooting and telemetry

#### 🛡️ Advanced Options
- Set:
  - **Default Domain**
  - **Security Lists**
  - **Resource Tags** for classification and automation

Click **`Next`** to proceed to database configuration.

---

### 3. 🗄️ Database Configuration

#### 🏷️ DB Identification
- **Container DB Name (CDB)**: Logical root container
- **Database Unique Name**: Globally unique name
- **Pluggable DB Name (PDB)**: First PDB inside the container

#### 🧬 Software Version
- Click **`Change Database Image`**
- Choose **Oracle 23ai** for latest AI-enabled DB capabilities

#### 🔐 Admin Credentials
- **Admin Password**: Create strong, secure password

---

### 4. 💾 Backup Configuration

#### 🔄 Enable Automatic Backups (optional)
Choose one of the following backup destinations:

##### 1. 🛡️ Recovery Service *(Recommended)*
- **Protection Policy**: Define RTO/RPO profiles
- **Real-Time Data Protection**
- **Backup Deletion Policy**
- **Scheduled Backup Day & Time**
- **Immediate First Backup** toggle

##### 2. 🧺 Object Storage *(Legacy option)*
- Lower cost, reduced backup features

---

### 5. ✅ Finalize & Create

- Click **`Create DB System`**
- Monitor status:  
  - `Provisioning → Available`
- Once active:
  - Navigate to **Container DB Details Page**
  - Click on the **Pluggable DB name** to access detailed PDB configuration

---

## 📌 Summary

This end-to-end provisioning sequence empowers administrators to deploy Oracle databases with a **high degree of control and precision**. By leveraging flexible compute shapes, storage architectures, IAM, and network segmentation, DB systems can be tailored to accommodate workloads ranging from small dev/test environments to mission-critical, high-availability RAC clusters.

Oracle 23ai support underscores the service’s readiness for **modern AI-powered database features**, while Recovery Service integration enhances **backup durability and disaster resilience**.

---

🧑‍🎓 *Provision confidently. Maintain securely. Scale intelligently.*
