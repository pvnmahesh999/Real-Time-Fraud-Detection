# 🚀 Real-Time Fraud Detection System

## 📌 Project Overview

This project is a **real-time fraud detection system** designed to analyze banking transactions and detect anomalies that indicate fraudulent activity. The system is built using **Apache Kafka, Apache Spark, PostgreSQL, MongoDB, Apache Airflow, and AWS Lambda**, leveraging an **XGBoost machine learning model** to classify fraudulent transactions.

### **🔹 Key Features:**

✔ **Real-time data ingestion** with Apache Kafka ✔ **Batch & streaming data processing** with Apache Spark ✔ **Fraud detection using XGBoost on Apache Spark** ✔ **Data storage in PostgreSQL & MongoDB** ✔ **ETL pipeline automation** with Apache Airflow ✔ **Scalable fraud detection API deployment** using AWS Lambda ✔ **CI/CD pipeline for seamless deployment**

---

## 📊 **Project Architecture**

```plaintext
+--------------------+       +------------------+       +------------------+
|   Transaction API  | ----> |  Apache Kafka    | ----> |  Apache Spark    |
|  (Simulated Data)  |       |  (Real-time Data)|       |  (Feature Eng.)  |
+--------------------+       +------------------+       +------------------+
                                                        |
                                                        v
                                      +-----------------------------+
                                      |  Fraud Detection Model (ML) |
                                      |   (XGBoost on Spark)        |
                                      +-----------------------------+
                                                        |
                                                        v
       +----------------+          +----------------+         +---------------+
       | PostgreSQL     | <------  |  MongoDB       | <------ |   AWS Lambda  |
       | (Structured)   |          | (Unstructured) |         | (Fraud API)   |
       +----------------+          +----------------+         +---------------+
```

---

## ⚙ **Step-by-Step Implementation Guide**

### **1️⃣ Data Collection & Ingestion** (Apache Kafka, REST API)

📌 **What We Did:**

- Simulated banking transactions using a **Python script**.
- Streamed transactions in **real-time** using **Apache Kafka**.

📌 **Implementation:**

- Created a Kafka topic `bank_transactions`.
- Produced streaming data to Kafka using `KafkaProducer` in Python.
- Consumed Kafka data using **Apache Spark Streaming**.

---

### **2️⃣ Data Storage** (PostgreSQL & MongoDB)

📌 **What We Did:**

- Stored structured transactional data in **PostgreSQL**.
- Stored unstructured fraud alerts & logs in **MongoDB**.

📌 **Implementation:**

- Designed relational tables in PostgreSQL for transactions.
- Used MongoDB for flexible fraud log storage.

---

### **3️⃣ Data Processing & Feature Engineering** (Apache Spark, PySpark)

📌 **What We Did:**

- Processed real-time transaction streams with **Apache Spark**.
- Extracted **features like transaction amount, location, time, user history**.
- Handled **missing values, data transformations**.

📌 **Implementation:**

- Used `PySpark` to process large-scale transaction data.
- Applied **feature selection & transformation**.

---

### **4️⃣ Fraud Detection Model Training** (XGBoost, Apache Spark MLlib)

📌 **What We Did:**

- Trained an **XGBoost fraud detection model**.
- Tuned **hyperparameters** for better fraud prediction.
- Integrated **Apache Spark MLlib** for distributed model training.

📌 **Implementation:**

- Used `train_test_split()` to split data.
- Trained XGBoost model with `Spark MLlib`.

---

### **5️⃣ API Deployment** (AWS Lambda)

📌 **What We Did:**

- Deployed the trained model as an **API** to classify transactions.
- Hosted the API using **AWS Lambda** for scalability.

📌 **Implementation:**

- Used Flask to serve predictions.
- Deployed on AWS Lambda for **low-latency fraud detection**.

---

### **6️⃣ ETL Pipeline & Automation** (Apache Airflow)

📌 **What We Did:**

- Automated **ETL workflows** for fraud detection model retraining.
- Scheduled pipeline execution using **Apache Airflow DAGs**.

📌 **Implementation:**

- Created Airflow tasks for **data extraction, transformation, loading (ETL)**.
- Automated **model retraining & monitoring**.

---

### **7️⃣ Monitoring & Visualization** (Power BI, Grafana)

📌 **What We Did:**

- Built a **real-time fraud detection dashboard** using **Power BI**.
- Monitored **transaction anomalies & fraud trends** in **Grafana**.

📌 **Implementation:**

- Connected **PostgreSQL to Power BI** for fraud trend reporting.
- Used Grafana to visualize **real-time streaming data from Kafka**.

---

## 📂 **Project Structure**

```plaintext
fraud-detection-system/
│-- data_ingestion/           # Kafka producer & consumer scripts
│-- data_processing/          # Spark jobs for feature engineering
│-- model_training/           # XGBoost model training scripts
│-- api/                      # Flask API for fraud detection
│-- automation/               # Airflow DAGs for ETL
│-- dashboards/               # Power BI & Grafana dashboards
│-- deployment/               # AWS Lambda deployment files
│-- README.md                 # Project documentation
```

---

## 🚀 **How to Set Up & Run the Project**

### **🔹 1️⃣ Clone the Repository**

```bash
git clone https://github.com/yourusername/fraud-detection-system.git
cd fraud-detection-system
```

### **🔹 2️⃣ Install Dependencies**

```bash
pip install -r requirements.txt
```

### **🔹 3️⃣ Start Kafka & PostgreSQL**

```bash
docker-compose up -d
```

### **🔹 4️⃣ Run Data Streaming Pipeline**

```bash
python data_ingestion/stream_transactions.py
```

### **🔹 5️⃣ Train the Fraud Detection Model**

```bash
python model_training/train_xgboost.py
```

### **🔹 6️⃣ Deploy API with AWS Lambda**

```bash
cd deployment/
zappa deploy
```

---

## 📊 **Demo & Usage**

- **Test Fraud Detection API:**

```bash
curl -X POST "https://your-api-url.amazonaws.com/predict" \
     -H "Content-Type: application/json" \
     -d '{"user_id": 123, "amount": 5000, "location": "NY"}'
```

- **Expected Response:**

```json
{
    "fraud_prediction": "High Risk"
}
```

---

## 📌 **Future Improvements**

- Implement **deep learning-based fraud detection with LSTMs**.
- Enhance **real-time alerting system with AWS SNS**.
- Expand data storage to **Google BigQuery & Snowflake**.

---

## 🤝 **Contributions**

If you’d like to contribute, feel free to open a **pull request** or raise an **issue**!

🚀 **Built with Apache Kafka, Spark, PostgreSQL, MongoDB, Airflow, AWS Lambda** 🚀

