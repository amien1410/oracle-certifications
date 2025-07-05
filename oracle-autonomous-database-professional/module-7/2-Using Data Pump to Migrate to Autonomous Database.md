# 🧰 **Using Data Pump to Migrate to Autonomous Database**

**Instructor:** Michelle

---

## 🎯 **Lesson Focus**

Learn how to use **Oracle Data Pump (expdp/impdp)** effectively for migrating databases to **Oracle Autonomous Database (ADB)**—with key **parameters**, **best practices**, and **cloud-specific tweaks**.

---

## ✅ **Why Use Data Pump?**

* Reliable for **full or partial migrations**
* Supports **parallelism**, **compression**, **fine-tuned control**
* Helps migrate from **Oracle 10.1+** and **older environments**

---

## 🧩 **Key Considerations Before Migration**

| Area                   | Best Practice                                                                                       |
| ---------------------- | --------------------------------------------------------------------------------------------------- |
| 👤 **User Role**       | Don't export as `SYSDBA`. Use regular users. Import using `ADMIN` in ADB.                           |
| 📁 **Parameter Files** | Always use `.par` files instead of long command lines for clarity & maintainability.                |
| 🧵 **File Chunks**     | Use `FILESIZE` to break large dumps (e.g., 5GB chunks) to ease upload, retry, and parallelism.      |
| 🏃 **Parallelism**     | Use `PARALLEL` for speed—match it to **ECPUs** (cloud) or **cores × 2** (on-prem).                  |
| 🔐 **Encryption**      | Remove **column-level encryption** before migration. ADB uses **tablespace-level encryption** only. |

---

## 🗜️ **Compression Tips**

| Option                                             | Trade-off                                        |
| -------------------------------------------------- | ------------------------------------------------ |
| `COMPRESSION=ALL` + `COMPRESSION_ALGORITHM=MEDIUM` | Recommended—balanced compression with good speed |
| `HIGH`                                             | Heavier CPU use, best for **slow internet**      |
| `LOW`                                              | Less compression, faster, but larger files       |

Requires **Advanced Compression** license (if not using Autonomous built-in tools).

---

## 🛠️ **Helpful Parameters for Migration**

| Parameter                             | Purpose                                                             |
| ------------------------------------- | ------------------------------------------------------------------- |
| `VIEWS_AS_TABLES`                     | Export only a **subset** of data using a **view**                   |
| `DUMPFILE=dir:%U.dmp`                 | Use **wildcards** for multiple files (especially in object storage) |
| `TRANSFORM=DISABLE_ARCHIVE_LOGGING:Y` | Speeds up import by skipping archive logging                        |
| `TRANSFORM=IOT_TABLE_TO_HEAP:Y`       | Converts **Index-Organized Tables** to **Heap**                     |
| `CONSTRAINT_USE_DEFAULT_INDEX=Y`      | Automatically **rename** constraints properly                       |
| `SEGMENT_ATTRIBUTES=NO`               | Removes segment-level settings—ADB handles them                     |
| `REMAP_TABLESPACE='*':'DATA'`         | Required—remaps all tablespaces to `DATA` in ADB                    |

---

## 🔍 **Restrictions to Watch For**

| Autonomous Type                     | Exclusions Required                                                                                              |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| 🏢 **Data Warehouse (ADW)**         | `INDEX`, `CLUSTER`, `INDEXTYPE`, `MATERIALIZED_VIEW`, `MATERIALIZED_VIEW_LOG`, `MATERIALIZED_ZONEMAP`, `DB_LINK` |
| ⚙️ **Transaction Processing (ATP)** | `CLUSTER`, `DB_LINK` only                                                                                        |

---

## 🚫 Common Pitfalls to Avoid

* ❌ Exporting as `SYSDBA`
* ❌ Failing to use parallel and file chunking
* ❌ Forgetting to remap tablespaces (`REMAP_TABLESPACE`)
* ❌ Keeping old encryption or segment attributes
* ❌ Forgetting to **exclude unsupported objects** (especially on ADW)

---

## 📌 Final Checklist for Smooth Data Pump Migration to ADB

* [ ] Use `par` files for clean commands
* [ ] Enable `COMPRESSION=ALL` and `PARALLEL`
* [ ] Upload chunked dump files to **Object Storage**
* [ ] Use `TRANSFORM`, `REMAP_TABLESPACE`, `SEGMENT_ATTRIBUTES`
* [ ] Run import as `ADMIN` (not SYS)
* [ ] Review exclusions list per ADB type

---
