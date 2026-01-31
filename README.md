# Inventory Safety Stock Analysis Dashboard

## Project Overview
This project delivers a Power BI dashboard designed to analyze **inventory stock levels** and compare **current safety stock** against a **recommended (optimized) safety stock**.  
The dashboard helps identify overstocking, stock risk, and opportunities for inventory optimization across products, plants, and business units.

![Inventory Level Report](https://github.com/Usama00004/Inventory-Level-Report/raw/main/Display%20Image.png)




## Objectives
- Monitor **unrestricted (available) inventory** over time
- Compare **current safety stock** vs **recommended safety stock (King’s SS)**
- Enable users to dynamically filter by material, product, plant, and business unit
- Support data-driven decisions for inventory optimization

##  Dataset Structure

### Dimensions
- `material_number` – Unique identifier for the material
- `product` – Product name
- `plant` – Manufacturing or storage location
- `business_unit` – Business grouping (e.g., Specialty Gases)
- `calendar_month` – Year-month in `YYYYMM` format

### Metrics
- `unrestricted_stock` – Actual physical inventory on hand
- `safety_stock` – Current safety stock maintained in ERP/APO
- `kings_ss` – Recommended safety stock (optimized / reduced buffer)

##  Data Preparation
- `calendar_month (YYYYMM)` is converted into a **date field** using the first day of the month (`YYYY-MM-01`)
- Additional derived fields:
  - Month Name (January, February, …)
  - Month Number (for sorting)
  - Year
- Month names are sorted correctly using **Sort by Column**

## 🎛️ Dashboard Filters (Global Filters)
All filters are interconnected to ensure consistent slicing across visuals:

- **Business Unit** – Filters available plants, products, and materials
- **Plant** – Filters inventory by location
- **Product** – Filters by chemical or hardware name
- **Material Number** – Primary driver (searchable dropdown)

Selecting a material dynamically updates all visuals.

##  Visualizations

### Current Stock Levels (Bar Chart)
- **Chart Type:** Bar / Column Chart
- **X-Axis:** Calendar Month
- **Y-Axis:** Unrestricted Stock (no aggregation)
- **Purpose:** Shows actual inventory trend over time

### Safety Stock Comparison (Line Chart)
- **Chart Type:** Line Chart (Dual Line)
- **X-Axis:** Calendar Month
- **Series:**
  - Current Safety Stock (`safety_stock`)
  - Recommended Safety Stock (`kings_ss`)
- **Purpose:** Highlights optimization gap between current and recommended buffers

## Tools & Technologies
- **Power BI Desktop**
- **Power Query (M language)** for data transformation
- **DAX** (minimal, model-driven approach)
- **Excel** as source data

##  Future Enhancements
- Add excess inventory calculation
- Highlight risk months (below safety stock)
- Add KPI cards for average inventory & variance
- Integrate forecast or consumption data


