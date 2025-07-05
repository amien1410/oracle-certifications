# 🤖 Oracle Autonomous Database: Select AI & GenAI

**Instructor:** Michelle
**Topic:** Natural Language to SQL using Select AI + LLMs
**Goal:** Query data with plain English using Generative AI (LLMs), no SQL required

---

## 🧠 Oracle’s GenAI Strategy

Oracle brings AI to the **entire enterprise tech stack**:

* 🔧 **Infrastructure** (with NVIDIA for model training)
* 🛡️ **Enterprise Data Security & Governance**
* 📦 **Platform Services** (to build your own GenAI apps)
* 📊 **Apps & UI Layers** (embedding GenAI into Oracle tools)

---

## 💡 What Is Select AI?

**Select AI** enables users to:

* Ask **natural language questions** (e.g., “Top 10 streamed movies?”)
* Get back:

  * ✅ SQL query
  * ✅ Result set
  * ✅ Narrative explanation

You don’t need:

* Schema knowledge
* SQL experience
* Table/column names

> Select AI handles the translation from **plain English to SQL**, executes the query, and shows the result.

---

## 🖥️ Use Case Demo: Select AI in APEX

### User Flow:

1. Ask a question in plain English
2. App sends it to Oracle Autonomous Database
3. LLM (large language model) understands the request
4. SQL is generated → result set returned
5. Use APEX UI to:

   * Sort/filter
   * Drill into charts
   * Download to Excel
   * View the generated SQL

> Select AI enhances APEX with conversational AI querying.

---

## ⚙️ Behind the Scenes: How It Works

### SQL Statement Format:

```sql
SELECT AI 'Show top 10 movies by total streams';
```

### Oracle DB handles:

* Prompt engineering
* Secure LLM call (e.g., OpenAI, Cohere, Llama)
* SQL query generation
* Result display

---

## 🧱 AI Profiles: Pluggable & Configurable

Use **AI Profiles** to configure:

* 🎯 Which **LLM** provider (Cohere, OpenAI, etc.)
* 📂 Which **schemas, tables, views** to include
* 🔐 Security, data governance

### Tooling:

Use `DBMS_CLOUD_AI` package to:

* Create AI profiles
* Define database objects (schemas/tables)
* Set model provider preferences

---

## 🔐 Data Privacy & Security

* Your **data stays within your OCI tenancy**
* Not shared with 3rd party LLM providers
* Enterprise-grade isolation & compliance
* GenAI is **secure by default**

---

## ✅ Benefits of Select AI

| Feature              | Benefit                                      |
| -------------------- | -------------------------------------------- |
| 🗣️ Natural Language | Ask data questions like a conversation       |
| 🧠 Generative SQL    | No need to learn SQL or data models          |
| 📦 APEX Integration  | Build AI into apps easily                    |
| 🔄 Flexible Models   | Use/fine-tune any supported LLM              |
| 🔐 Secure            | Keeps data private in your cloud environment |

---

## 📌 Final Example

**Natural question:**

> "Find the top customer segments for George Clooney movies."

**Select AI does:**

1. Parses question using LLM
2. Builds optimized SQL
3. Returns results + SQL preview

---

## 🎓 Summary

* Select AI uses **natural language + LLMs** to **query Oracle data** easily
* Build **AI-powered apps** using APEX or SQL Developer
* Secure, scalable, and customizable through **AI profiles**
* Future-proof: Supports new/fine-tuned LLMs

> 🧩 “Ask the database” – and let Select AI do the work.

---
