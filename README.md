# 🏥 Healthcare Data Pipeline (Galaxy Schema Edition)

## 📌 Project Overview
This project showcases the design and implementation of a **Healthcare Data Pipeline** using **Microsoft Fabric**, **Delta Lake**, and **PySpark**.  
The goal is to build a **modern data warehouse** capable of handling healthcare data efficiently, enabling analytics on **patients, visits, prescriptions, and insurance claims**.

The project simulates a **real-world healthcare scenario** where multiple sources (patient visits, prescriptions, and insurance claims) are integrated into a **Galaxy Schema** (a variation of the star schema).  
The data is ingested in layers (**Bronze → Silver → Gold**) to ensure proper separation of raw data, cleaned data, and analytics-ready tables.

---

 ![Image Alt](https://github.com/elmagry123/Healthcare-Data-Pipeline/blob/d05cb64b32187f5bc2b292d264d96fc518d73b77/1754752014694.jpeg)

## 🛠️ Tech Stack
- **Microsoft Fabric OneLake** → Storage and Lakehouse management.  
- **PySpark** → Data processing and transformations.  
- **Delta Lake** → Optimized table format with ACID transactions and schema enforcement.  
- **Parquet** → Intermediate data storage in Silver Layer.  
- **Galaxy Schema** → Data warehouse modeling technique.  

---

## ⚙️ Pipeline Architecture
The pipeline follows the **Medallion Architecture**:

1. **Bronze Layer (Raw Data):**  
   - Stores raw ingestion files as they arrive (e.g., JSON, CSV).  
   - No transformation applied at this stage.  

2. **Silver Layer (Cleaned Data):**  
   - Data cleaning and standardization.  
   - Stored as **Parquet files** for efficiency.  
   - Examples: removing nulls, renaming columns, standardizing data types.  

3. **Gold Layer (Analytics-Ready Data):**  
   - Modeled into **fact** and **dimension** tables using **Galaxy Schema**.  
   - Stored as **Delta tables** to support ACID transactions and schema evolution.  
   - Used for BI dashboards and advanced analytics.  

---

## 🗂️ Data Model (Galaxy Schema ERD)
The project implements a **Galaxy Schema** with **3 Fact Tables** and **8 Dimension Tables**.


### **Fact Tables**
1. **fact_visits**  
   - Tracks patient visits, including doctor, department, diagnosis, treatment, and cost.  

2. **fact_prescriptions**  
   - Records patient prescriptions, including medication, dosage, frequency, and duration.  

3. **fact_insurance_claims**  
   - Captures insurance claims, including provider, claim status, and amount.  

### **Dimension Tables**
1. **dim_patient** → patient demographics (name, age, gender, city).  
2. **dim_doctor** → doctor details.  
3. **dim_department** → hospital departments.  
4. **dim_diagnosis** → diagnosis types.  
5. **dim_treatment** → treatment details.  
6. **dim_date** → calendar table with granular time breakdown.  
7. **dim_medication** → medication details.  
8. **dim_insurance_provider** → insurance company details.  

---

## 📊 Key Features & Achievements
- Built a **Healthcare Data Warehouse** on top of **Delta Lake**.  
- Implemented **3 Fact Tables** and **8 Dimension Tables** for healthcare analytics.  
- Used **Galaxy Schema** for flexible modeling of multiple business processes.  
- Data processed using **PySpark** for scalability and performance.  
- Silver Layer optimized with **Parquet**, Gold Layer stored in **Delta Lake**.  
- Designed to support **scalable BI dashboards** and advanced data analysis.  

---

## 📑 Example Use Cases
With this data model, analysts can answer questions like:  
- What is the average cost of treatments per department?  
- Which doctors handle the most patient visits?  
- What are the most frequently prescribed medications by diagnosis?  
- What percentage of insurance claims are denied vs approved?  
- How do patient demographics correlate with specific diagnoses?  

---



## 📌 Author
**Abdelrahman Hussein**  
- 💼 Data Engineer  
- 📍 Egypt  

---

