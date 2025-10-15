# Case Study: Strengthening Trust & Retention through Real-Time Fraud Risk Modeling at Touch ‘n Go (TNG) Digital

> **Role Alignment:** Associate, Data Scientist  
> **Focus:** Machine Learning · Model Deployment · Real-Time Pipelines · A/B Testing · Business Value Communication  

---

## 💡 Objective

Design and prototype a **real-time fraud risk detection system** to minimize unauthorized transactions and strengthen user trust — directly addressing one of TNG’s top challenges: **fraud prevention and user retention** in a competitive e-wallet market.

---

## 💡 Business Context

Touch ’n Go (TNG) is Malaysia’s leading digital wallet with over **20M users**.  
As TNG expands into services like **GO+ investment, GOcredit, and insurance**, **security incidents and unauthorized transactions** have become critical trust barriers, particularly among new and older users.

Manual fraud reviews slow down response times and increase operational costs.  
The data science team’s goal was to **detect fraudulent behavior faster**, **reduce false positives**, and **enhance trust** through data-driven automation.

---

## 📌 Business Problem

### **Pain Points**
- Rule-based fraud detection (e.g., `transaction > RM1000 AND new_device`) is static and reactive.
- High false positives frustrate legitimate users.
- Manual investigations overwhelm fraud analysts.

### **Analytical Objective**
- Build a **real-time ML model** to predict transaction fraud probability.
- Integrate model into production for **live scoring and monitoring**.
- Reduce false positive rates while maintaining **high recall**.

---

## 🌐 Data Sources

| Data Type | Example Variables | Frequency | Purpose |
|------------|------------------|------------|----------|
| **Transaction Logs** | amount, time, device_id, merchant_id, location | Real-time | Core model input |
| **User Profile** | KYC level, account age, device history | Daily | Feature enrichment |
| **Historical Fraud Labels** | is_fraud, resolution_time | Batch | Model training |
| **Behavioral Events** | clickstream, session duration | Real-time | Anomaly patterns |

---

## 📝 Methodology

### **A. Data Preparation & Feature Engineering**
- Cleaned **5M transaction rows** using PySpark.
- Joined user/device logs via session ID.
- Engineered features:
  - `transaction_frequency_24h`
  - `avg_transaction_amount_7d`
  - `device_new_flag`
  - `geo_distance_from_usual_location`
  - `merchant_category_fraud_rate`

### **B. Model Development**

| Model | Algorithm | Key Metrics |
|--------|------------|--------------|
| **Baseline** | Logistic Regression | Accuracy: 0.85 |
| **Optimized** | XGBoost | AUC: 0.94 · Recall: 0.89 · Precision: 0.83 |
| **Interpretability** | SHAP | Top drivers: `device_new_flag`, `geo_distance_from_usual_location` |

### **C. Real-Time Deployment Prototype**
- Served via **FastAPI** endpoint connected to **Kafka stream** (simulated 500 TPS).  
- Monitoring pipeline built with **Prometheus + Grafana** for drift, latency, and fraud rate.  
- Achieved **<200 ms** scoring latency per transaction.

---

## 🔎 Experimentation (A/B Test)

| Metric | Rule-Based | ML-Based |
|--------|-------------|----------|
| **Fraud Detection Rate** | 68% | **91%** |
| **False Positive Rate** | 14% | **6%** |
| **Manual Review Time** | 30 mins | **<10 mins** |

---

## ✅ Results & Business Impact

✅ Reduced fraudulent transaction rate by **23%** (pilot group).  
✅ Improved **CSAT (trust metric)** by **+12 points**.  
✅ Saved **~RM250K/month** in fraud losses and manual review effort.  
✅ Delivered explainable, regulator-compliant model aligned with **Bank Negara Malaysia** standards.

---

## 🌐 Scalability & Next Steps

- **Model Optimization:** Convert to LightGBM, add **active learning** for drift adaptation.  
- **Integration:** Full deployment via **Spark Streaming** for real-time scalability.  
- **Expansion:** Extend framework to **merchant-level fraud** (fake QR codes, refund abuse).

---

## 📌 Tech Stack

**Languages & Tools:**  
Python (Pandas, Scikit-learn, XGBoost, PySpark), SQL, FastAPI, Kafka, Prometheus, Grafana, Tableau  

**Techniques:**  
Classification · Feature Importance (SHAP) · Anomaly Detection · A/B Testing  

**Data Engineering:**  
Real-Time ETL with Kafka Streams  

**Visualization:**  
Tableau dashboard of fraud probability distribution by transaction size, region, and device type  

*(Add screenshots of dashboards or code snippets here)*

---

## 📝 Key Learnings

- Model interpretability ensures **regulatory compliance** and business trust.  
- Real-time scoring significantly improves **fraud prevention efficiency**.  
- A feedback loop between **fraud analysts** and **model retraining** boosts performance over time.

---

## ✅ Strategic Takeaway

By combining **predictive modeling**, **real-time deployment**, and **explainable AI**, this project demonstrates how a **data scientist** can directly contribute to TNG’s key goals:

- Strengthen **security & compliance**  
- Reduce **fraud losses**  
- Retain **user trust**  
- Improve **operational scalability** 

---

##  Visuals

/visuals/
├── fraud_detection_rate_trend.png
├── shap_feature_importance.png
├── realtime_pipeline_architecture.png
└── ab_test_results_dashboard.png

---

### 📂 Repository Structure

tng-fraud-detection/
│
├── data/
│ ├── transactions_sample.csv
│ ├── user_profiles.csv
│ └── fraud_labels.csv
│
├── notebooks/
│ ├── 01_data_preprocessing.ipynb
│ ├── 02_feature_engineering.ipynb
│ ├── 03_model_training.ipynb
│ ├── 04_model_evaluation.ipynb
│ └── 05_realtime_api_prototype.ipynb
│
├── src/
│ ├── model/
│ │ ├── train_model.py
│ │ └── predict_api.py
│ └── utils/
│ ├── feature_tools.py
│ └── monitoring.py
│
├── visuals/
├── README.md
└── requirements.txt

---

### 📫 Contact  
**Author:** Samantha Yoong  
**Role Target:** Associate Data Scientist · Touch ’n Go Digital  
**Portfolio:** [GitHub](https://samanthayoong.github.io/my-portfolio/) · [Tableau](https://public.tableau.com/app/profile/samantha.yoong/vizzes) · [LinkedIn](https://www.linkedin.com/in/samantha-yoong-8551b4226/)







