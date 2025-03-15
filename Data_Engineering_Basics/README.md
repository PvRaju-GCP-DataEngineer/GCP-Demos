# Data Engineering Overview 

## 📌 What is Data Engineering?
Data Engineering focuses on designing and building systems that enable the collection, storage, and analysis of data at scale. It ensures data is clean, accessible, and efficiently processed for business intelligence, analytics, and AI applications.

---

## 🔹 Types of Data  
Data can be categorized based on structure and processing mode:

### 1️⃣ **Based on Structure**  
- **Structured Data** – Organized, stored in tables (SQL Databases). Example: Transactions, Customer Records.  
- **Semi-Structured Data** – Partially organized (JSON, XML, CSV, Logs). Example: API responses, Sensor Data.  
- **Unstructured Data** – No fixed format (Images, Videos, Text). Example: Social Media, Emails, Audio.  

### 2️⃣ **Based on Processing Mode**  
- **Batch Data** – Processed in bulk at scheduled intervals. Example: Daily ETL jobs.  
- **Streaming Data** – Processed in real time as events occur. Example: IoT sensor data, Live Analytics.  

---

## 🔄 **Batch vs. Streaming Data Processing**
| Feature       | Batch Processing  | Streaming Processing |
|--------------|------------------|----------------------|
| **Latency**   | High (Minutes/Hours) | Low (Milliseconds) |
| **Data Input** | Large volumes at once | Continuous event streams |
| **Use Case**  | Payroll processing, Monthly reports | Fraud detection, Real-time dashboards |
| **Tech Stack** | Apache Spark, Hadoop, Airflow | Apache Kafka, Flink, Google Dataflow |

---

## 🔀 **How Data Pipelines Work? (ETL/ELT Workflow)**  
A data pipeline automates the flow of data from raw sources to meaningful insights.

### **Workflow of a Data Pipeline**
```
Raw Data → Ingestion → Storage → Processing → Analytics & BI → Insights
```
1️⃣ **Data Ingestion** – Collects data from APIs, databases, files, or streaming services.
2️⃣ **Storage** – Stores raw or structured data in cloud databases or data lakes.
3️⃣ **Processing** – Uses ETL (Extract, Transform, Load) or ELT (Extract, Load, Transform) techniques to clean and structure the data.
4️⃣ **Analytics & BI** – Utilizes tools like Looker Studio or Tableau to analyze data.
5️⃣ **Insights & Decision Making** – Data is ready for use in dashboards, reports, and ML models.

### **1️⃣ Data Ingestion**
- **Batch Data Sources**: CSV, Databases, APIs, Cloud Storage (GCS, AWS S3)
- **Streaming Data Sources**: Kafka, Google Pub/Sub, Webhooks, IoT Devices

### **2️⃣ Data Processing & Transformation**
- **ETL (Extract, Transform, Load)**: Structured transformation before storage
- **ELT (Extract, Load, Transform)**: Load raw data first, then transform
- **Tools**: Apache Spark, Google Dataflow, Apache Beam, Databricks

### **3️⃣ Data Storage & Warehousing**
- **Structured Data**: Google BigQuery, Snowflake, Amazon Redshift
- **Semi-Structured Data**: Google BigTable, MongoDB
- **Unstructured Data**: Google Cloud Storage (GCS), AWS S3

### **4️⃣ Data Analytics & Visualization**
- **BI Tools**: Looker Studio, Tableau, Power BI
- **ML & AI Models**: Google Vertex AI, TensorFlow, AutoML
- **Use Cases**: Customer segmentation, Sales forecasting, Anomaly detection

### **5️⃣ Workflow Orchestration & Monitoring**
- **Automation**: Apache Airflow, Prefect, Google Workflows
- **Monitoring**: Datadog, Prometheus, Grafana

---

A **Data Pipeline** moves data from source to storage, processes it, and makes it ready for analysis. Here are the steps:  

### **Step 1: Data Ingestion (Collecting Data)**  
📌 Data comes from different sources:  
- **Apps & Websites** → Clickstream data, event logs  
- **IoT Devices** → Sensor data, smart home data  
- **Databases** → Sales transactions, employee records  

📌 **How to Ingest Data in GCP?**  
- **Streaming Data (Real-time updates)** → **Pub/Sub**  
- **Batch Data (Processed periodically)** → **Cloud Storage, Transfer Service**  

🛠 **Tools Used:**  
✅ **Pub/Sub** – For real-time data ingestion  
✅ **Cloud Storage (GCS)** – To store batch data  

---

### **Step 2: Data Storage (Saving Data for Processing)**  
After ingestion, data needs to be stored securely for further processing.  

📌 **Where to store data?**  
- **Cloud Storage (GCS)** – For all types of data (CSV, JSON, images, etc.)  
- **BigQuery** – For analyzing large structured datasets  
- **Cloud Spanner** – For scalable databases  
- **BigTable** – For handling massive semi-structured data  

🛠 **Tools Used:**  
✅ **Google Cloud Storage (GCS)** – Stores raw data  
✅ **BigQuery** – Handles structured data for analysis  
✅ **BigTable** – Optimized for big semi-structured data  

---

### **Step 3: Data Processing & Analysis**  
Once data is stored, it must be processed before use.  

📌 **How do we process data?**  
- **Batch Processing (Processing large amounts of data in intervals)**  
  - Example: Processing daily sales reports  
  - **Tool:** Apache Beam (Dataflow)  

- **Streaming Processing (Processing data in real-time)**  
  - Example: Detecting fraud in credit card transactions  
  - **Tool:** Apache Kafka, Apache Flink, Google Dataflow  

🛠 **Tools Used:**  
✅ **Dataflow** – Processes streaming & batch data  
✅ **Dataproc** – Runs Apache Spark & Hadoop for big data processing  

---

### **Step 4: Data Exploration & Visualization**  
After processing, data is analyzed using dashboards and reports.  

📌 **Tools for visualization:**  
- **Looker Studio (formerly Data Studio)** – Easy-to-use dashboard  
- **Datalab & Jupyter Notebooks** – For advanced data exploration  
- **Prebuilt ML APIs** – For AI-based analysis (Vision API, Speech API)  

🛠 **Tools Used:**  
✅ **Looker Studio** – For dashboards & reports  
✅ **Datalab** – For Python-based data analysis  
✅ **BigQuery ML** – For machine learning on structured data  

---

## **3. Example: End-to-End Data Pipeline on GCP**  

Let’s say we want to analyze user activity on an e-commerce website.  

📌 **Step-by-step pipeline:**  
1. **Ingest Data** → Pub/Sub collects website clickstream events  
2. **Store Data** → Google Cloud Storage saves raw event logs  
3. **Process Data** → Dataflow cleans and structures the data  
4. **Load to Warehouse** → BigQuery stores processed data  
5. **Analyze & Visualize** → Looker Studio creates reports  

🖼 **Diagram:**  
```
User Activity → Pub/Sub → GCS → Dataflow → BigQuery → Looker Studio
```

## 🎯 **Essential Data Engineering Tools**

### **📁 Storage & Warehousing**
- **Google BigQuery** – Fully managed, serverless data warehouse  
- **Snowflake** – Cloud data platform for analytics  
- **Amazon Redshift** – Data warehouse for structured analytics  

### **⚙️ Data Processing & Transformation**
- **Apache Spark** – Distributed data processing engine  
- **Google Dataflow (Apache Beam)** – Real-time & batch data processing  
- **Databricks** – Cloud-based big data processing  

### **🔄 Workflow Orchestration & Automation**
- **Apache Airflow** – ETL pipeline scheduling & monitoring  
- **Google Workflows** – Automate data processes in GCP  

### **📡 Messaging & Streaming**
- **Apache Kafka** – Event streaming platform for real-time analytics  
- **Google Pub/Sub** – Event-driven messaging service  

### **📊 Data Analytics & Machine Learning**
- **Looker Studio (Google Data Studio)** – BI reporting & dashboards  
- **Vertex AI** – AI/ML model training & deployment  
- **TensorFlow, PyTorch** – AI framework for deep learning  

---

## 🚀 **Real-World Applications of Data Engineering**
- **Netflix** – Recommender system based on user behavior & streaming data  
- **Amazon** – Predictive analytics for inventory & customer recommendations  
- **Uber** – Real-time tracking of rides, pricing algorithms  
- **Google Maps** – Traffic predictions & route optimization  

