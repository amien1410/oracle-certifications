# 🔒 Setting Up ACLs and Private Endpoints in Oracle Autonomous Database

**Instructor:** Kamryn Vinson
**Course:** Oracle University – Autonomous Database Dedicated Infrastructure

---

## 🔐 Access Control Lists (ACLs)

Access Control Lists (ACLs) restrict which IPs can connect to an Autonomous Database.

### 🛡️ Why Use ACLs?

* **By default**, databases are publicly accessible.
* ACLs block **all traffic** **except** whitelisted IPs.
* **Essential** for environments requiring strict security and access control.

### 🔧 ACL Configuration Options:

* Individual IP Addresses
* **CIDR Blocks**
* **Virtual Cloud Networks (VCN)**
* **VCN by OCID**
* Combination of the above

> ⚠️ ACLs also affect services like:
>
> * SQLDeveloper Web
> * Oracle APEX
> * Oracle Machine Learning Notebooks

### 💡 ACL Notes:

* Can be configured at creation or on existing DB
* Survive **restores** (not overwritten)
* Whitelist entries can be edited anytime

---

## 🌐 Private Endpoints

Private Endpoints ensure **zero public internet exposure** for Autonomous Database.

### ✅ Key Benefits:

* Keeps **all traffic private** (even within OCI)
* Works for cloud-based apps or on-premises environments
* **No need for Transit Routing** when set correctly
* Requires **clone** of DB to enable (cannot apply to existing DB directly)

---

### 🧱 Requirements to Use Private Endpoints:

| Component                 | Requirement                               |
| ------------------------- | ----------------------------------------- |
| VCN                       | Must be in the same **region** as the DB  |
| Private Subnet            | With **default DHCP options**             |
| Network Security Group(s) | At least **one NSG** for private endpoint |

---

## 🔥 Network Security Groups (NSG)

NSGs are like **firewalls** that define **Ingress/Egress rules** for your ADB.

### 📌 Example:

* Allow **Ingress TCP 1522** (ADB listens on this port)

### NSG Features:

* Up to **5 NSGs per ADB**
* Flexibility to modify after provisioning
* Rule-based security, e.g. allow only from app server IP range

---

## 🧪 Demo Flow Summary

1. Go to **OCI Console → Edit ACLs**
2. Add IPs, CIDRs, or VCNs
3. Save & enable whitelist enforcement
4. For private endpoint:

   * Clone the existing DB
   * Use a private subnet & VCN with NSG configured
5. Use NSG to define port/protocol-based rules

---

## 🧭 When to Use What?

| Use Case                             | Recommendation        |
| ------------------------------------ | --------------------- |
| Restrict access by IPs               | Use ACLs              |
| Prevent any public internet exposure | Use Private Endpoints |
| Fine-grained security per port       | Use NSGs              |

---

### 🏁 Summary

* ACLs restrict **who** can access ADB
* Private endpoints restrict **how** they can access ADB
* NSGs restrict **what ports/services** are available
* All three are **essential tools** for secure OCI architectures

---
