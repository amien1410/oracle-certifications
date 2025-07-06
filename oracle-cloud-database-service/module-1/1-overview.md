# 📘 Oracle Base Database Service on Virtual Machine DB Systems – Summary

👩‍🏫 *Prepared by a diligent and curious learner exploring Oracle Cloud Infrastructure (OCI)*

## 🧠 Overview

Oracle Base Database Service on Virtual Machine (VM) DB Systems enables deployment of fully-featured Oracle databases in the cloud. It runs on flexible VM shapes and supports enterprise-grade features, automation, security, and licensing options, tailored for various business needs.

---

## ☁️ Key Features

- Deploy **Oracle databases (19c, 21c, 23ai)** globally using OCI.
- Supports **single-instance** and **two-node RAC** configurations.
- Offers **co-managed** infrastructure:  
  - Oracle manages infrastructure  
  - You manage database VM content via **UI Console** or **API**
- Designed for **Enterprise Edition** and **Standard Edition** workloads.

---

## ⚙️ Automation & Lifecycle Management

- Automates critical DBA tasks:
  - Provisioning
  - Scaling
  - Patching
  - Backup & Recovery
  - High Availability (HA) & Disaster Recovery (DR) with **Data Guard**
- Reduces human error and DBA workload
- Enables faster deployment of environments

---

## 🔐 Security

- **Multilevel Security** with:
  - Always-on encryption
  - **Oracle Data Safe**
- Transparent Data Encryption (TDE) included across all tiers
- Full control: **You have root access** to your VM

---

## 💸 Licensing Models

### 1. **License Included (LI)**  
Ideal for:
- New applications
- Customers without existing Oracle licenses

Includes:
- Oracle Database Enterprise Edition
- Enterprise Manager Packs  
- Elastic **OCPU metering** for cost efficiency

### 2. **Bring Your Own License (BYOL)**  
Ideal for:
- Migrating existing workloads to cloud

Benefits:
- Use existing Oracle licenses in the cloud
- Extra features included without additional licensing:
  - TDE
  - Diagnostics Pack
  - Tuning Pack
  - Data Masking
  - Subsetting Pack
  - Real Application Testing
- **Oracle Support Rewards**: Get 25% credit of cloud spend to offset on-prem support bills

---

## 🧾 Licensing Tiers

| Tier                              | Includes                                                                 |
|-----------------------------------|--------------------------------------------------------------------------|
| **Standard Edition 2**           | 3 PDBs, Machine Learning, Spatial & Graph                               |
| **Enterprise Edition (EE)**      | Data Guard, Management Packs for Tuning & Data Masking                  |
| **EE High Performance (HP)**     | Partitioning, Adv. Compression/Security, Lifecycle Mgmt Packs           |
| **EE Extreme Performance (XP)**  | Everything above + RAC, Active Data Guard, In-Memory DB                 |

> **Note**: For RAC or Exadata deployments with LI, EE Extreme Performance is mandatory.

---

## 🧮 Compute & Storage

- **Shapes**: Choose from **Ampere**, **AMD**, and **Intel Flexible Shapes**
- **Scaling**:
  - OCPU and memory based on shape
  - Online scaling of storage:
    - Up to 80TB (data)
    - Up to 20TB (redo logs)
  - More storage = higher I/O performance
- **Billing**:
  - **Per-second OCPU billing** based on selected license tier
- **Backup Options**:
  - Default: Oracle Recovery Service
  - Alternative: Object Storage (same cost)

---

## 🚧 Limitations & Notes

- **Single-node VM ↔️ Two-node RAC VM scaling is not supported**
- **Two-node RAC** deployments require:
  - **Extreme Performance license**
  - **Rolling CPU scaling** (one VM at a time)

---

## ✅ Why Use Oracle Base Database Service?

- Fast, secure, and flexible cloud deployment
- Combines powerful Oracle features with cloud automation
- Ideal for modern, scalable, mission-critical applications

---

🧑‍🎓 *This summary was created to assist students and professionals quickly grasp the essentials of Oracle Base Database Service on VMs. Happy learning!*
