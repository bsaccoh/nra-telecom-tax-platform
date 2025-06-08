# NRA Telecom Tax Collection System

Design, Implementation, and Analysis of a Tax Collection System for the National Revenue Authority (NRA):

An end-to-end data engineering and analytics platform to assist the **National Revenue Authority (NRA)** of Sierra Leone in calculating and collecting taxes from **telecom services** (voice, SMS, data, recharge). This project focuses on **Orange Sierra Leone** as a case study.

---

## 🌟 Project Objectives

- Design and implement a tax computation system using telecom service data.
- Automate the data ingestion, transformation, and storage process using Python and MySQL.
- Apply the **Medallion Architecture** to ensure scalable and structured data flow (Bronze, Silver, Gold layers).
- Generate accurate tax summary reports based on predefined service charge and tax rules.
- Improve transparency and accountability in telecom tax collection.

---

## 📋 Project Specifications

### 📂 File Format
- All service data files from Orange are provided in `.add` flat file format.
- Each file represents a specific service (e.g., `voice.add`, `sms.add`, `data.add`, `mobile_money.add`).
- Example of file format (cbs_cdr_voice_20250501000000_123_101_842713.add)

### ⚙️ Architecture
- **Medallion Architecture**:
  - **Bronze Layer**: Raw ingestion of `.add` files into `bronze_voice`, `bronze_sms`, `bronze_data`.
  - **Silver Layer**: Cleaned, structured tables like `silver_usage`, `silver_money_transfers`.
  - **Gold Layer**: Summarized and analytics-ready tables such as `gold_tax_summary`, `gold_service_aggregates`.

### 🛠️ Technology Stack

| Component       | Technology      |
|----------------|------------------|
| Programming     | Python 3        |
| Database        | MySQL 8+        |
| ETL Framework   | Custom Python scripts (pandas, mysql.connector) |
| Data Architecture | Medallion (Bronze, Silver, Gold) |
| Input File Type | `.add`    |
| Output Format   | SQL reports / CSV exports / dashboard-ready tables |

---

## 🧱 Database Schema Overview

### Bronze Tables
- `voice_cdr_records`
- `sms_cdr_records`
- `data_cdr_records`
- `recharge_cdr_record`

### Silver Tables
- `silver_usage`
- `silver_money_transfers`

### Gold Tables
- `gold_tax_summary`
- `gold_service_aggregates`

---

## 📊 Sample Tax Computation Logic

| Service       | Tax Rate | Computation Basis   |
|---------------|----------|--------------------------|
| Voice         | 15%       | Based on minutes charged |
| SMS           | 15%       | Based on message count   |
| Data          | 15%       | Based on MB used         |
| Recharge      | 15%     | Based on Recharge Amounts   |
| Mobile Money  | 15%     | Based on transfer value |
---
