# ⚡ Oracle NoSQL Database Cloud Service: Throughput

Welcome to the **Oracle NoSQL Database Cloud Service – Throughput** lesson.  
In this session, we’ll explore how throughput is provisioned and consumed, the flexibility it offers for development, and how operations are billed based on usage.

---

## 📊 What Is Throughput Provisioning?

In Oracle NoSQL, **throughput** is provisioned in two units:

| Type           | Unit        | Purpose                                   |
|----------------|-------------|-------------------------------------------|
| 🔄 **Read Unit**  | 1 RU       | One eventually consistent read of up to 1KB |
| ✍️ **Write Unit** | 1 WU       | One write of up to 1KB                    |

---

## 🔁 Eventual vs Absolute Consistency

| Consistency Type     | Description                                                                 | Cost         |
|----------------------|-----------------------------------------------------------------------------|--------------|
| ✅ **Eventual**       | Default. Updates propagate over time; may return *stale* data               | 1 Read Unit  |
| 🔒 **Absolute**       | Guarantees latest value for each read (strong consistency)                  | 2 Read Units |

> Use **eventual** for better performance and cost-efficiency.  
> Use **absolute** when data accuracy is critical.

---

## ⏳ Time To Live (TTL)

Oracle NoSQL supports automatic **data expiration**:

- 🔁 **Table-level TTL** – Default aging rule for all records  
- 📦 **Record-level TTL** – Custom expiration per row  

This helps manage data lifecycle and optimize storage.

---

## 🔌 Access via API & SQL

You can interact with NoSQL data through:

- 🛠️ **APIs** (Java, Python, REST, etc.)
- 🧾 **SQL** with:
  - JSON support
  - Schema interoperability
  - Complex filtering: `AND`, `OR`, `NOT`, etc.

---

## 💸 Billing Model

Oracle NoSQL Cloud uses a **usage-based billing** approach:

| Billed Item     | Metric        |
|-----------------|---------------|
| ⚡ Throughput    | Read/Write Units (RU/WU) |
| 📦 Storage       | Gigabytes (GB) per hour  |

> You are **not** billed for underlying CPU, memory, or IOPS.

---

## 🔍 How Operations Consume Units

| Operation   | Unit(s) Used                   |
|-------------|--------------------------------|
| 🔄 Read      | Read Units (RU)               |
| ✍️ Write     | Write Units (WU)              |
| 📝 Update    | Read Units + Write Units      |
| ❌ Delete    | Read Units + Write Units      |

---

## 🧾 Summary

| Feature                   | Description                                            |
|---------------------------|--------------------------------------------------------|
| 📏 Throughput Provisioning | Scale RUs and WUs as needed                            |
| 🔁 Consistency             | Choose between eventual and absolute consistency       |
| ⏳ Time to Live (TTL)      | Auto-expire data at table or record level              |
| 🔌 Flexible Access         | Full API and SQL support for varied use cases          |
| 💸 Usage-Based Billing     | Only pay for provisioned RUs/WUs and storage           |

---

## 🙌 Thanks for Learning!

This concludes our lesson on **Oracle NoSQL Database Cloud Service Throughput**.  
You’re now better equipped to optimize cost and performance when building apps on Oracle Cloud!
