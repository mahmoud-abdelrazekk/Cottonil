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

## Application Screenshots

The screenshots below cover the core analytics views and the decision-support modules. They are arranged in a two-column gallery for better readability.

<table>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142641.png" alt="Sales & Profit Analytics" width="100%"><br><b>Sales & Profit Analytics</b><br><sub>Monthly sales trends, category contribution, and top / low-margin products.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142701.png" alt="Branch & Regional Performance" width="100%"><br><b>Branch & Regional Performance</b><br><sub>Regional sales distribution and top-performing branches.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142714.png" alt="Inventory & Supply Chain" width="100%"><br><b>Inventory & Supply Chain</b><br><sub>Category-level stock position and delivery lead-time indicators.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142742.png" alt="Customer Demographics & RFM" width="100%"><br><b>Customer Demographics & RFM</b><br><sub>Customer age bands, cohort behaviour, and RFM segmentation.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142756.png" alt="Channels, Payments & Returns" width="100%"><br><b>Channels, Payments & Returns</b><br><sub>Payment mix, channel performance, and return analysis.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142828.png" alt="Warehouse-to-Branch Allocation" width="100%"><br><b>Warehouse-to-Branch Allocation</b><br><sub>Allocation workflow and operational inputs for stock rebalancing.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20142845.png" alt="Allocation Decision Support" width="100%"><br><b>Pricing & Margin Model</b><br><sub>Price and discount scenario controls with estimated margin and profit impact.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144344.png" alt="Customer Win-Back" width="100%"><br><b>Customer Win-Back</b><br><sub>Customer retention targeting and campaign-oriented outputs.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144448.png" alt="High-Value Refund Review" width="100%"><br><b>High-Value Refund Review</b><br><sub>Statistical review signals and flagged refund records.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144513.png" alt="Seasonal Demand Forecasting" width="100%"><br><b>Seasonal Demand Forecasting</b><br><sub>Random Forest demand forecast, planning indicators, and forecast table.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144553.png" alt="Bilingual Data Copilot" width="100%"><br><b>Bilingual Data Copilot</b><br><sub>Executive Copilot interface and supported question categories.</sub></td>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144615.png" alt="Copilot – Suggested Questions" width="100%"><br><b>Copilot – Suggested Questions</b><br><sub>Quick prompts for common operational and commercial questions.</sub></td>
  </tr>
  <tr>
    <td width="50%" valign="top" align="center"><img src="images/Screenshot%202026-11-02%20144624.png" alt="Copilot – Interactive Analysis" width="100%"><br><b>Copilot – Interactive Analysis</b><br><sub>Bilingual question workflow for querying analytical data.</sub></td>
    <td width="50%"></td>
  </tr>
</table>

[Browse all 13 screenshots](images/)

## Project Notebook

[**Cottonil Analysis Notebook**](notebooks/Cottonil_Data_Analysis_and_AI_Alignment.ipynb)

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
├── images/                 # Application screenshots
│   └── (13 PNG screenshots)
└── notebooks/
    └── Cottonil_Data_Analysis_and_AI_Alignment.ipynb
```

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

### 4. Configure the application

Make sure the application can access its required local resources before launching.

### 5. Run the application

```bash
streamlit run app.py
```

## Project Status

The main Streamlit application, dependency list, project documentation, screenshots, and analysis notebook are published. A final end-to-end run in the target environment should still be performed.

---

<div align="center">

**Cottonil Enterprise Analytics | Built with Python & Streamlit**

</div>
