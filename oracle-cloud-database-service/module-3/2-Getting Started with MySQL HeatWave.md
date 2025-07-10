# 🚀 Getting Started with MySQL HeatWave on Oracle Cloud

In this module, we explored how to **set up and use MySQL HeatWave** — Oracle's fully managed, high-performance MySQL cloud service. This guide covers everything from infrastructure requirements to provisioning and connecting to your MySQL HeatWave system via the OCI Console.

---

## 🧰 Prerequisites for MySQL HeatWave

To get started, you'll need:

1. ✅ An **Oracle Cloud Infrastructure (OCI) account**
2. ✅ A valid **OCI tenancy** and **user login**
3. ✅ A **compartment** to store resources
4. ✅ Required **IAM policies** for HeatWave (created by admin)
5. ✅ A **Virtual Cloud Network (VCN)** with public and private subnets

---

## 🏗️ Key Components of a MySQL HeatWave System

- A **compute instance**
- Oracle Linux OS
- MySQL Enterprise Edition (latest)
- Virtual NIC attached to a **private subnet**
- High-performance **block storage**

🔍 The architecture typically consists of:
- A **public subnet** for SSH access via a Linux bastion host
- A **private subnet** where MySQL HeatWave resides securely

---

## 🛠️ Step-by-Step: Creating the MySQL HeatWave DB System

### 🔹 Step 1: Start the Provisioning Process
- Go to **MySQL Database System** via the OCI Console
- Click **Create Database System**

### 🔹 Step 2: Basic Information
- Choose **compartment**
- Enter **name** and **description**
- Select **standalone system** and enable **MySQL HeatWave**

### 🔹 Step 3: Admin Credentials
- Create an admin user (not `mysql.sys`)
- Provide and confirm a **secure password**

### 🔹 Step 4: Configure Networking
- Select your **VCN** and **private subnet**
- OCI recommends using the default placement and shape
- Keep the default block storage and enable **scheduled backups**

### 🔹 Step 5: Finalize
- Click **Create**
- Wait for the status to turn from “Creating” (🟡) to “Active” (🟢)

---

## 💻 Setting Up a Compute Instance (Bastion Host)

- Go to **Compute > Instances**, then click **Create Instance**
- Choose:
  - Name and compartment
  - Oracle Linux (default)
  - Same **VCN** as your DB system
  - Enable **Public IP**
  - Upload or generate an **SSH key**
- Click **Create** → wait until instance status becomes **Running**

---

## 🔐 Configuring VCN Ingress Rules

To allow client connections:

- Go to **Networking > Virtual Cloud Networks**
- Select your VCN > **Security Lists**
- Click **Add Ingress Rules**
  - **Source CIDR**: IP range of your public subnet (or custom)
  - **Protocol**: TCP
  - **Destination Port Range**: `3306` (MySQL Classic), `33060` (MySQL X)

---

## 🔗 Connecting to MySQL HeatWave

### 🧪 Option 1: MySQL Shell (on Compute Instance)

1. SSH into your compute instance.
2. Install **MySQL Shell**.
3. Use the endpoint IP (from DB details) to connect:
   ```bash
   mysqlsh --uri admin@<MySQL-endpoint-IP>
   ```

### 🖥️ Option 2: MySQL Workbench (via SSH Tunnel)

To connect to your MySQL HeatWave database using **MySQL Workbench** over SSH:

**Configuration settings:**

| Setting            | Value                                       |
|--------------------|---------------------------------------------|
| **SSH Hostname**    | Public IP of your compute instance          |
| **SSH Username**    | `opc`                                       |
| **SSH Key File**    | Path to your SSH private key                |
| **MySQL Hostname**  | Private IP of the MySQL HeatWave instance   |
| **MySQL Port**      | `3306` (MySQL Classic) or `33060` (X Protocol) |
| **Username**        | Your admin user                             |
| **Password**        | Admin user password                         |

👉 Use the **Standard TCP/IP over SSH** connection method.

---

### 📦 Test with Sakila Sample Database

To test and validate your MySQL HeatWave setup, you can load the **Sakila** sample database, which includes:

- ✅ Views  
- ✅ Stored procedures  
- ✅ Triggers  

This is an excellent resource for practicing and evaluating MySQL features.

---

### 📘 Summary

In this module, you learned how to:

- ✅ Set up the **OCI networking and security** environment  
- ✅ Provision a **MySQL HeatWave DB system**  
- ✅ Launch and configure a **compute instance** (bastion host)  
- ✅ Connect using **MySQL Shell** or **MySQL Workbench**  
- ✅ Apply **VCN security rules** for safe and secure access  
- ✅ Load and test with **sample data like Sakila**

You're now ready to work with MySQL HeatWave on Oracle Cloud! 🚀
