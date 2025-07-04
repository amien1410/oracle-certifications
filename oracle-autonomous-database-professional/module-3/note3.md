# 🚀 Provisioning Dedicated Resources in Oracle Autonomous Database

**Instructor:** Linda Foinding
**Lesson Focus:** Provisioning Autonomous Database on Dedicated Exadata Infrastructure
**Platform:** Oracle University

---

## 🛠️ Overview: What You’ll Learn

This lesson walks through:

* Provisioning **Exadata infrastructure**
* Creating **Virtual Cloud Network (VCN)** & **subnets**
* Setting up **Autonomous Container Databases (ACDs)**
* Deploying **Autonomous Databases (ADBs)** on dedicated infrastructure

---

## 📦 Step 1: Provision Exadata Infrastructure

### 👤 Log In

* Use **Fleet Administrator** credentials.
* Navigate to **Autonomous Database** service in OCI Console.
* Go to **Autonomous Exadata Infrastructure** > click **Create**.

### 🧾 Configuration

* Choose a meaningful **display name**
* Select **Availability Domain**
* Choose **shape** (e.g., Quarter Rack, 92 OCPUs)
* Select appropriate **subnet**
* Customize the **maintenance schedule** if desired (e.g., first Sunday of the quarter, 12–4AM UTC)
* Choose **license type**
* Click **Create**

---

## 🌐 Step 2: Set Up Virtual Cloud Network (VCN)

### 🔧 VCN & Subnets

* CIDR block: `10.0.0.0/16`
* Add **two subnets**:

  * `10.0.0.0/24` for **Exadata**
  * `10.0.1.0/24` for **Application**

### 🔒 Security Lists

* Create one for each subnet
* Open required ports for:

  * Database access (Exadata subnet)
  * Internet traffic (Application subnet, optional)

### 🌍 Internet Gateway (Optional)

* Add for outbound internet access from application subnet
* Route to `0.0.0.0/0` (or restrict it for security)

---

## 📤 Step 3: Provision Autonomous Container Database (ACD)

### 👤 Login as Fleet Admin

* Navigate to **Autonomous Transaction Processing** > **Autonomous Container Database**
* Click **Create Autonomous Container Database**

### ⚙️ Configuration Options

* Choose **Release Update (RU)** strategy
* Set **maintenance schedule**
* Choose **backup retention policy** (up to 60 days)

### ✅ Finalize

* Click **Create** to deploy your **Autonomous Container Database (ACD)**

---

## 🧱 Step 4: Provision Autonomous Database (ADB)

### 👤 Login as Database User

* Choose **Autonomous Transaction Processing** or **Autonomous Data Warehouse**
* Select the **user’s compartment**
* Click **Create Autonomous Database**

### ⚙️ Database Settings

* Enter a **name**
* Select **Dedicated Infrastructure**
* Choose the **compartment** hosting the ACD (e.g., Fleet)
* Pick a **container database** from the dropdown

### ✅ Launch ADB

* Click **Create Autonomous Database**

---

## 🧠 Key Takeaways

* Dedicated Exadata infrastructure setup requires **networking** and **compartment** planning.
* OCI provides flexibility in **maintenance windows**, **resource allocation**, and **network security**.
* You only **pay for running databases**, not for allocated infrastructure like ACDs or AVMs.
* **ACD** allows multiple ADBs to share update strategy and backup policies.
* Oracle’s model supports **self-service provisioning** for developers and DBAs, within defined boundaries.

---
