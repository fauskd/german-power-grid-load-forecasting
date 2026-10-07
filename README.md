# ⚡ German Power Grid Load Analytics & Demand Forecasting

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-3.4+-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

An end-to-end Big Data Analytics and Machine Learning project analyzing and forecasting electrical grid power demand in Germany based on weather conditions (temperature, wind, solar) and temporal factors. 

This project demonstrates a production-style **Medallion Data Lakehouse Architecture (Bronze → Silver → Gold)** built with **PySpark**, featuring feature engineering, predictive modeling, metric evaluation, and interactive visual reporting.

---

## 📌 Business & Executive Summary

Grid operators and energy traders require highly accurate power load forecasts to maintain grid stability and optimize renewable energy integration. 

* **Objective**: Ingest multi-variable energy and weather data, perform feature engineering, build predictive ML models to forecast power demand ($MW$), and visualize actual vs. forecasted demand.
* **Core Business Impact**: Minimizes load variance, supports grid stability analysis, and provides actionable visual metrics for energy decision-makers.

---
 
## 🏗️ Architecture & Data Flow (Medallion Pattern)

The analytical pipeline follows a structured 3-tier data architecture:
1. **Bronze Layer (Raw Storage)**: Untouched raw ingestion stored in columnar `.parquet` format for efficient compression and query performance.
2. **Silver Layer (Cleaned & Feature Engineered)**: Data cleaning, handling null values, and feature extraction (e.g., `hour`, `month`, `is_weekend` derived from timestamps) normalized using PySpark `StandardScaler`.
3. **Gold Layer (Curated Analytics)**: Machine learning predictions linked with actual load metrics for business consumption and visual analytics.

---

## 🛠️ Tech Stack & Analytical Tools

* **Data Processing & Analytics**: PySpark (SQL Functions, Spark DataFrame API)
* **Machine Learning**: PySpark MLlib (`VectorAssembler`, `StandardScaler`, `GBTRegressor`)
* **Data Visualization**: Plotly (Interactive visual analytics)
* **Storage Formats**: Apache Parquet (Columnar Storage)
* **Environment**: Jupyter Notebook / Python

---

## 📊 Analytics & Key Insights

* **Weather-Load Sensitivity**: Lower ambient temperatures drive significant heating demand spikes, whereas elevated solar radiation correlates with reduced net grid load during midday hours.
* **Temporal Patterns**: Grid demand exhibits peak load behavior during weekday morning and early evening business hours, dropping significantly on weekends (`is_weekend = 1`).
* **Model Evaluation Metric**: Evaluated using **Root Mean Squared Error (RMSE)** to measure $MW$ load deviation against ground-truth grid consumption.

---

## 💻 Installation & Local Setup

### 1. Clone the Repository
```bash
git clone [https://github.com/fauskd/german-power-grid-load-forecasting.git](https://github.com/fauskd/german-power-grid-load-forecasting.git)
cd german-power-grid-load-forecasting
pip install pyspark pandas plotly numpy
```
