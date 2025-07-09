# ☁️ Provisioning Exadata Cloud@Customer: Overview & Network Architecture

🎯 **Lesson Goals**:
After this lesson, you’ll be able to:
- ✅ Describe the **provisioning and activation** process of Exadata Cloud@Customer (C@C)
- ✅ Create the **VM Cluster Network**
- ✅ Provision the **Exadata VM Cluster**
- ✅ Identify and confirm **resource allocations** and **networking details**

---

## 🧠 Key Concept: Cloud@Customer (C@C)

**Exadata Cloud@Customer** delivers the power of Oracle Exadata Cloud Service **in your own data center**, while Oracle manages the infrastructure remotely—giving you the benefits of cloud automation without moving your data offsite.

---

## 🌐 Network Architecture of Exadata Cloud@Customer

The network setup of Cloud@Customer is **similar to public cloud deployments**, but with some **key differences** due to the infrastructure residing in your on-premises environment.

### 💡 Major Differences from Public Cloud

| Area | Public Cloud | Cloud@Customer |
|------|--------------|----------------|
| Infrastructure | Hosted in OCI DC | Hosted in your DC |
| VCN Location | In your OCI tenancy | **Not** in your tenancy (managed separately) |
| Network Type | VCN-based | **VM Cluster Network** |
| OCI Access | Over internet or FastConnect | Over **VPN** via control plane servers |

---

## 🧱 Components of the Network Architecture

### 1. **Client and Backup Subnets**
- Used for app & admin connections to VMs and DBs
- Exist **in your corporate network**
- No need for FastConnect, VPN, or gateways
- Managed inside a **VM Cluster Network** (not inside a VCN)

### 2. **VM Cluster Network**
- Logical container for client & backup subnets
- One VM Cluster Network = One VM Cluster
- Supports multiple VM cluster networks per C@C system

---

### 3. **Control Plane Network**
- A **VPN-based virtual private network** connecting:
  - OCI region ↔️ Control Plane Servers in the C@C rack
- Purpose:
  - Secure automation
  - Remote monitoring & management
  - Access to OCI services (object storage, telemetry, identity, logging)

### 4. **Administration Network**
- Internal network connecting:
  - Exadata servers & switches ↔️ Control Plane Servers
- Fully internal to the **C@C rack**
- Used for:
  - Cloud automation
  - Oracle admin tasks
- ⚠️ Does **not** connect directly to your corporate network
- Requires IPs **not used elsewhere in your network**

---

## 🌐 External Connections

- **Control Plane Servers** connect to OCI region using the control network
- To support DNS & NTP, the **Exadata infrastructure connects indirectly** to your corporate network via control plane servers
- ✅ You **must register hostnames/IPs** in your corporate DNS for all client & backup interfaces

---

## 🔐 OCI Access & Management

- Oracle Cloud Operations uses:
  - **OCI Web Console**
  - **OCI REST APIs**
- Access via:
  - **HTTPS** through secure automation tunnel
  - **SSH**, if necessary
- Managed from Oracle’s **service tenancy** through the Admin VCN

---

📌 **Summary**:
- Exadata Cloud@Customer gives you public cloud capabilities **inside your data center**
- Core networking is familiar but adapted for on-premises
- VM Cluster Network replaces VCN
- Control and Admin networks enable secure Oracle-managed operations
- DNS/NTP integration with your corporate network is essential

✅ Up Next: Learn how to create VM Cluster Network and provision the VM cluster.
