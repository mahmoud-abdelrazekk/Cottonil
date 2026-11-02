# Cottonil | Enterprise Analytics & AI Platform

An integrated Streamlit business-intelligence platform for exploring Cottonil's sales, customers, branches, inventory, returns, and supply-chain operations, with a collection of interactive decision-support applications.

> **Data & privacy:** The business datasets are not included in this public repository. The application expects the owner to place authorized data files in the local folders described below. Do not commit customer, employee, payroll, transaction, or other confidential company data.

## Platform overview

The application is organized into two main areas:

### 1. Enterprise Analytics
- Sales and revenue performance
- Product and category analysis
- Branch and governorate performance
- Inventory and supply-chain indicators
- Customer behaviour and RFM segmentation
- Sales channels, payment methods, and returns

### 2. AI Applications & Decision Support
1. **Warehouse-to-Branch Allocation** — rule-based allocation recommendations and estimated logistics timing.
2. **Pricing & Margin Model** — interactive what-if pricing and margin simulation using configured category elasticity assumptions.
3. **Customer Win-Back** — RFM-based customer grouping and campaign scenarios with assumed response rates.
4. **High-Value Refund Review** — statistical review flags based on refund-value thresholds.
5. **Seasonal Demand Forecasting** — Random Forest forecasting evaluated with walk-forward validation and compared with a seasonal-naive baseline.
6. **Keyword Direct-Query Copilot** — keyword-driven questions answered through DataFrame aggregations; this is not a generative LLM.

## Technology stack

- Python
- Streamlit
- Pandas and NumPy
- Plotly
- scikit-learn for Random Forest forecasting
- PyArrow (optional, for processed Parquet tables)

## Repository structure

```text
Cottonil/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── COTTONIL_Data/
│   └── 02_TABLES/
│       └── README.md
└── processed_data/        # Optional local Parquet tables; not committed
```

## Data setup

The app loads data from either:

- `processed_data/` — optional preprocessed Parquet tables; or
- `COTTONIL_Data/02_TABLES/` — source CSV tables.

For the CSV fallback, the application expects these files:

```text
branches.csv
products_catalog.csv
sku_variants.csv
warehouses.csv
suppliers.csv
customers.csv
sales_orders.csv
sales_order_items.csv
monthly_stock.csv
delivery_shipments.csv
sales_returns.csv
```

The data must follow the schema and column names expected by the application. The original company data is intentionally excluded. Obtain permission before using or sharing any business dataset.

## Run locally

1. Clone the repository:

   ```bash
   git clone https://github.com/mahmoud-abdelrazekk/Cottonil.git
   cd Cottonil
   ```

2. Create and activate a virtual environment:

   **Windows**
   ```powershell
   python -m venv .venv
   .venv\Scripts\activate
   ```

   **macOS / Linux**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Add your authorized source CSV files to `COTTONIL_Data/02_TABLES/` (or your prepared Parquet files to `processed_data/`).

5. Start the application:

   ```bash
   streamlit run app.py
   ```

## Methodology notes & limitations

Some modules are analytical decision-support tools rather than predictive ML models. Allocation recommendations use configured business rules and logistics assumptions. Pricing simulations use configured elasticity assumptions and should not be interpreted as causal price experiments. Win-back response rates are scenario assumptions, not trained customer-response predictions. Refund review identifies statistical outliers; a flagged refund is not proof of fraud or preventable loss.

The forecasting module uses a Random Forest with walk-forward validation and a seasonal-naive benchmark. Forecasts are planning estimates and should be reviewed alongside operational context and data quality.

Inventory data is reported at the grain available in the source tables; do not interpret category/location-level stock as live SKU-level inventory.

## Project status

This repository contains the application and setup documentation. The cleaned analysis notebook, screenshots, and any safe synthetic demonstration data may be added in a later update. No private source datasets are published here.

## License

No license has been added yet. All rights remain with the repository owner unless a license is explicitly included.
