# 🍕 Pizza Sales Lakehouse

An end-to-end data engineering project built on Databricks, implementing a Lakehouse architecture using the Medallion pattern (Bronze → Silver → Gold) to process and analyze pizza sales data.

---

## 🏗️ Architecture

| Layer  | Description |
|--------|------------|
| Bronze | Raw CSV ingestion into Delta tables |
| Silver | Data cleaning, validation, and standardization |
| Gold   | Star schema with fact and dimension tables for analytics |

---

## 📁 Project Structure
\```

├── init_lakehouse.ipynb
├── bronze_layer.ipynb
├── silver/
│   ├── silver_orchestration.ipynb
│   ├── silver_orders.ipynb
│   ├── silver_order_details.ipynb
│   ├── silver_pizzas.ipynb
│   └── silver_pizza_types.ipynb
├── gold/
│   ├── gold_orchestration.ipynb
│   ├── dim_pizza.ipynb
│   ├── dim_date.ipynb
│   └── fact_sales.ipynb
└── orchestration.ipynb

\```

---

## 🗂️ Data Model (Gold Layer)

- `fact_orders` — raw transactional fact table capturing order lines with quantity and timestamps  
- `fact_sales` — transactional fact table at order line level, including quantity and revenue  
- `dim_pizza` — enriched pizza attributes (name, category, ingredients, size, price)  
- `dim_date` — calendar dimension for time-based analysis  

---

## ⚙️ Tech Stack

- **Platform**: Databricks  
- **Processing**: PySpark & SQL  
- **Storage**: Delta Lake  
- **Architecture**: Medallion (Bronze / Silver / Gold)  

---

## 🚀 Pipeline Flow

1. Ingest raw CSV data into Bronze layer  
2. Clean and validate data in Silver layer  
3. Build star schema (fact + dimensions) in Gold layer  

---

## ▶️ How to Run

1. Run `init_lakehouse.ipynb` to initialize schemas and storage  
2. Upload source CSV files to the Bronze layer  
3. Run `orchestration.ipynb` to execute the full pipeline  

---

## 📊 Key Features

- End-to-end ETL pipeline  
- Data validation and cleaning in Silver layer  
- Star schema design in Gold layer  
- Revenue calculation and business-ready dataset  
