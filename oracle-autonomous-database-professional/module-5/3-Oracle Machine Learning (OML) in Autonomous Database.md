# 🧠 Oracle Machine Learning (OML) in Autonomous Database

**Instructor:** Hope Fisher
**Topic:** Automating ML model development using AutoML and OML4Py in Oracle Autonomous Database

---

## 🚀 Why Use Oracle Machine Learning?

Typical machine learning development is:

* Manual
* Time-consuming
* Resource-intensive

**Oracle AutoML** simplifies this process by:

* **Automating** feature selection
* **Selecting** the best algorithm(s)
* **Tuning** hyperparameters automatically

You can do this:

* With **Python API** via **OML4Py**
* Or through a **UI-based experience** via **OML AutoML UI**

---

## 🔧 What is OML4Py?

OML4Py is:

* Oracle’s **Python API** for in-database machine learning
* Supports **AutoML pipeline** for:

  * Classification
  * Regression

### OML4Py AutoML Key Functions:

1. **Algorithm Ranking** – Based on predictive potential
2. **Feature Selection** – Removes noise, improves accuracy
3. **Model Building + Hyperparameter Tuning** – Done automatically

> 🚀 AutoML saves time & compute by avoiding exhaustive brute-force searches.

---

## 📊 OML AutoML UI Pipeline: Overview

| Step                           | Function                             |
| ------------------------------ | ------------------------------------ |
| **1. Algorithm Selection**     | Ranks top-performing ML algorithms   |
| **2. Adaptive Sampling**       | Reduces dataset size intelligently   |
| **3. Feature Selection**       | Picks the most predictive features   |
| **4. Model Tuning**            | Finds best hyperparameter settings   |
| **5. Feature Impact Analysis** | Ranks features by their contribution |

---

## 🔬 Phase Deep Dive

### 1. 🔍 **Algorithm Selection**

* Extracts data characteristics (shape, distribution, correlation)
* Uses **meta-learning models** to **predict best algorithm**
* Ranks top-K algorithms by expected performance

### 2. 🎯 **Feature Selection**

* Reduces data size
* Removes irrelevant/noisy variables
* Improves training speed and model accuracy

#### Process:

* Calculate feature statistics (meta features)
* Use multiple ranking techniques
* Predict model quality per feature subset
* Iterate and refine the optimal feature set

### 3. ⚙️ **Model Tuning**

* Focuses on **hyperparameter optimization**
* Uses **gradient descent** techniques for tuning
* Avoids slow and costly brute-force grid searches

---

## ✅ Benefits of Using OML AutoML

| Feature       | Advantage                   |
| ------------- | --------------------------- |
| 🚀 Automation | Save time, less manual work |
| 📈 Accuracy   | Improved model performance  |
| 📉 Efficiency | Reduced compute costs       |
| 🔁 Repeatable | Consistent modeling process |

---

## 🧾 Summary

Oracle’s AutoML, integrated into Autonomous Database through OML4Py and the AutoML UI:

* Automates the full machine learning pipeline
* Reduces time and resources
* Empowers data scientists and analysts to **build better models faster**

---

🎓 *That concludes the lesson on Oracle Machine Learning with Autonomous Database. Thanks for watching!*
