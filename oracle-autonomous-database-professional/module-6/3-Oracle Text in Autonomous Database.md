# 🧠 Oracle Text in Autonomous Database

**Instructor:** Michelle
**Topic:** Full-text search, indexing, and advanced document analysis using Oracle Text in Oracle Autonomous Database.

---

## 🔍 What is Oracle Text?

**Oracle Text** is a built-in feature in **all Oracle Database editions** that provides:

* Full-text indexing and search
* Document analysis
* Relevance scoring and linguistic capabilities
* Support for structured and unstructured data (SQL, JSON, XML, PDFs, etc.)

> ✅ **Enabled by default** in Oracle Autonomous Database

---

## 📚 Why Use Oracle Text?

| Feature                      | Description                                                               |
| ---------------------------- | ------------------------------------------------------------------------- |
| 🔠 Full-text search          | Search over CLOBs, VARCHAR2, JSON, XML, Word/PDF files, and web documents |
| 🌐 Multi-language support    | Handles documents in many languages                                       |
| 📊 Relevance scoring         | Returns documents based on ranking (e.g. `SCORE(1) > 50`)                 |
| 🧩 Indexing binary documents | Extracts text from Word, PDF, PowerPoint, etc.                            |
| 🧠 Advanced NLP features     | Includes classification, clustering, entity recognition, sentiment        |

---

## 💾 How Text is Indexed

### ✅ For plain text:

```sql
CREATE INDEX idx_text ON reviews(description) 
INDEXTYPE IS CTXSYS.CONTEXT;
```

Querying:

```sql
SELECT * FROM reviews WHERE CONTAINS(description, 'hello world', 1) > 0;
```

### ✅ For JSON:

```sql
CREATE SEARCH INDEX jtext_index ON reviews(jtext);
```

Querying:

```sql
SELECT * FROM reviews 
WHERE JSON_TEXTCONTAINS(jtext, '$.description', 'hello world');
```

You can use **`json_textcontains`** to locate keywords inside JSON fields.

---

## 🔄 Relational Joins in Text Queries

Oracle Text lets you **combine JSON/Full-text with relational joins**:

* Join tables (e.g. users + reviews + business)
* Filter by text AND structured columns (like postal code, IDs)

Example:

```sql
SELECT u.username, r.text 
FROM users u, reviews r, business b
WHERE JSON_TEXTCONTAINS(r.jtext, '$.description', 'sushi')
AND r.userid = u.userid
AND r.business_id = b.id
AND b.postal_code LIKE '8911%';
```

---

## 🧱 Indexing Pipeline: Behind the Scenes

| Stage           | Function                                                |
| --------------- | ------------------------------------------------------- |
| 📥 Data store   | Fetches documents (DB, file system, web URLs)           |
| 🧹 Filter       | Converts binary formats (e.g. PDFs) to plain text       |
| 🪚 Sectioner    | Splits into paragraphs, sentences                       |
| ✂️ Lexer        | Breaks text into words for indexing                     |
| 🧱 Index engine | Builds index files (layout, stoplists, wordlists, etc.) |

> Most stages are **customizable** via Oracle’s **extensibility framework** using SQL, PL/SQL, Java, or C.

---

## ✨ Features Beyond Search

| Feature                  | Description                                                           |
| ------------------------ | --------------------------------------------------------------------- |
| 🎯 Highlighting          | Shows search terms highlighted in text                                |
| 🧩 Snippets              | Returns only relevant sections of documents                           |
| 📚 Gist/Theme extraction | Determines what the document is about (semantic topics)               |
| 🧑‍🎓 Entity recognition | Detects names, dates, places, phone numbers, etc.                     |
| 🤖 Classification        | Groups documents via supervised or unsupervised learning (clustering) |
| 💬 Sentiment analysis    | Determines tone of the document (positive/negative)                   |

---

## 📦 Working with External Documents

Oracle Text can also index:

* 📄 Documents stored as **file paths** in DB
* 🌐 Documents linked by **URLs** (web crawling)
* 🧾 Document formats: **HTML, XML, JSON, Word, PDF, PPT**, etc.

> Oracle automatically **extracts content**, parses structure, and prepares it for indexing.

---

## 📈 Faceted Navigation

A **powerful UI feature** beyond SQL:

* Allows **summary filtering** across dimensions (e.g. categories, date ranges)
* Returns results in **JSON or XML**
* Example:

  * Searching “Christmas” → Results: 460 hits

    * 🎵 Music: 265
    * 🎬 Movies: 192
    * 📚 Books: 3

---

## 🔑 Summary: Why Use Oracle Text?

| Advantage                  | Description                                                             |
| -------------------------- | ----------------------------------------------------------------------- |
| 🔎 Enterprise-grade search | Powerful, customizable full-text indexing and querying                  |
| 🧠 AI + ML capabilities    | Built-in classification, entity detection, sentiment analysis           |
| 🌍 Document versatility    | Handles many formats and sources (relational, JSON, binary, web)        |
| 🔧 Developer-friendly      | Use SQL, JSON queries, and combine with traditional Oracle skills/tools |
| 🛡️ Autonomous & scalable  | Part of Oracle Autonomous Database—auto-patching, scaling, HA           |

---

Now you're equipped to build apps that **search, understand, and classify** documents—at scale, securely, and smartly.
