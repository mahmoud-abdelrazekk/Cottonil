# Local data directory

Place authorized Cottonil source CSV files in this directory. The application reads from `COTTONIL_Data/02_TABLES/`.

Expected source tables include branches, products_catalog, sku_variants, warehouses, suppliers, customers, sales_orders, sales_order_items, monthly_stock, delivery_shipments, and sales_returns.

**Do not commit actual business datasets here.** This folder is tracked only to document the expected local path. The root `.gitignore` excludes CSV, Excel, and Parquet data files.
