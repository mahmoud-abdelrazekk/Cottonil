<div align="center">

# Cottonil | Enterprise Analytics & AI Platform

**An integrated business intelligence and decision-support platform for Cottonil**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?logo=streamlit)](https://streamlit.io/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org/)
[![Plotly](https://img.shields.io/badge/Plotly-Interactive%20Charts-3F4F75?logo=plotly)](https://plotly.com/python/)

[**Repository**](https://github.com/mahmoud-abdelrazekk/Cottonil) · [**Analysis Notebook**](notebooks/Cottonil_Data_Analysis_and_AI_Alignment.ipynb)

</div>

---

## Project Overview

Cottonil Enterprise Analytics is a Streamlit-based platform designed to turn operational and commercial data into clear business insights. It combines enterprise reporting, exploratory analysis, forecasting, and interactive decision-support applications in one place.

The project is organized into two main areas:

### 1. Enterprise Analytics
- Sales, revenue, discount, and profitability analysis
- Product, SKU, and category performance
- Branch and geographic performance
- Customer behaviour and RFM segmentation
- Inventory, warehouse, and supply-chain indicators
- Returns, refunds, delivery, and operational analysis

### 2. AI Applications & Decision Support

| Application | Purpose | Method |
|---|---|---|
| Warehouse-to-Branch Allocation | Suggests allocation and replenishment actions | Business rules and operational assumptions |
| Pricing & Margin Model | Simulates price, discount, and margin scenarios | What-if calculations using configured assumptions |
| Customer Win-Back | Segments customers for retention campaigns | RFM segmentation and scenario assumptions |
| High-Value Refund Review | Highlights unusual refund records for review | Statistical thresholds |
| Seasonal Demand Forecasting | Estimates future category demand | Random Forest with walk-forward validation and seasonal-naive benchmark |
| Keyword Direct-Query Copilot | Answers supported questions from analytical data | Keyword/rule-based DataFrame aggregations |

> **Methodology note:** Not every application is a trained machine-learning model. Allocation, pricing, win-back scenarios, and refund review use rules, statistical screening, or configured assumptions. The forecasting module is the main supervised ML workflow. The Direct-Query Copilot is not a generative LLM.

## Screenshots

Screenshots from the latest published application version will be added here after capturing the current interface. Older prototype screenshots were intentionally excluded so the README does not misrepresent the current application.

## Data Analysis Notebook

The analysis notebook is available here:

[**Cottonil Data Analysis & AI Alignment Notebook**](notebooks/Cottonil_Data_Analysis_and_AI_Alignment.ipynb)

It documents:
1. Source data inventory and schema / data-dictionary audit
2. Missing values, duplicates, primary keys, and relationships
3. Sales, payment, returns, delivery, and supply-chain reconciliation
4. Data preparation and enterprise exploratory analysis
5. Customer RFM segmentation
6. Category-level demand forecasting with Random Forest and a seasonal-naive benchmark
7. Findings, limitations, and alignment with the six applications

The notebook contains no saved cell outputs. It requires the authorized source CSV files to run locally.

## Technology Stack

- **Python**
- **Streamlit** — interactive application
- **Pandas / NumPy** — data preparation and analysis
- **Plotly** — interactive visualizations
- **Scikit-learn** — Random Forest forecasting
- **Matplotlib** — notebook visual analysis
- **PyArrow** — optional Parquet data support

## Repository Structure

```text
Cottonil/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
└── notebooks/
    └── Cottonil_Data_Analysis_and_AI_Alignment.ipynb
```

## Data Privacy & Setup

The original Cottonil business datasets are **not included** in this public repository. Customer, employee, payroll, transaction, and other confidential records must remain private and must not be committed to GitHub.

You must have authorization to use the source data. The repository's `.gitignore` excludes local business data and common environment files.

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/mahmoud-abdelrazekk/Cottonil.git
cd Cottonil
```

### 2. Create a virtual environment

**Windows (PowerShell)**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the authorized data files

Place the required CSV files in `COTTONIL_Data/02_TABLES/`, or provide the prepared Parquet tables in the local `processed_data/` directory.

### 5. Run the application

```bash
streamlit run app.py
```

## Important Analytical Limitations

- Some sales orders have missing customer identifiers. They remain part of company-level totals but cannot be assigned to an individual RFM customer.
- The available monthly stock data is at category/location/month grain; it should not be interpreted as live SKU-level stock.
- A recorded return does not by itself prove that returned goods were received back into sellable inventory.
- Purchase-order records should not be treated as confirmed received quantities without receiving evidence.
- Pricing and win-back scenarios use assumptions and are not causal estimates of customer or market response.
- Statistical refund flags are review signals, not proof of fraud.
- Forecasts are planning estimates and should be interpreted with their validation results, coverage, and data grain.

## Project Status

The main Streamlit application, dependency list, privacy rules, setup documentation, and analysis notebook are published. Current-version application screenshots and a final end-to-end run using the authorized local datasets remain to be added/verified.

---

<div align="center">

**Cottonil Enterprise Analytics | Built with Python & Streamlit**

</div>
