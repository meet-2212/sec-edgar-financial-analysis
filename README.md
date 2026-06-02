# SEC EDGAR Financial KPI Analysis

## Overview
This project analyzes the impact of COVID-19 on corporate financial health
using SEC EDGAR DERA Financial Statement Data Sets. The analysis spans
pre-COVID, COVID impact, and post-COVID recovery periods to identify
structural shifts in key financial performance indicators (KPIs) across
publicly traded companies and industry sectors.
 
## Business Question
**"Which financial KPIs derived from SEC EDGAR filings were most impacted
by COVID-19, how did they recover Post-COVID, and do these patterns
vary by industry sector?"**

## Dashboard Link
https://dbc-ed455dba-c535.cloud.databricks.com/dashboardsv3/01f15ec886871c359a75aa047bdc5371/published?o=7474646254263004

## Target Audience
- Asset Management Firms
- Trading & Hedge Funds
- Real Estate Firms & REITs
- Credit & Risk Analysts
## Tech Stack
- **Cloud Platform:** Databricks (Serverless)
- **Languages:** Python, SQL
- **Data Source:** SEC EDGAR DERA Financial Statement Data Sets
- **Visualization:** Interactive HTML Dashboard
- **Version Control:** GitHub
## Data Coverage
- **SEC EDGAR filings:** Q1 2018 — Q4 2024 (28 quarters)
- **Total filings analyzed:** 139,696 (after outlier filtering)
- **Period Labels:**
  - Pre-COVID: Q1 2018 — Q4 2019 (8 quarters)
  - COVID Impact: Q1 2020 — Q2 2020 (2 quarters)
  - Post-COVID Recovery: Q3 2020 — Q4 2024 (18 quarters)
## Delta Tables Produced
 
### Raw Ingestion (56 tables)
| Table Pattern | Description | Rows (avg) |
|---------------|-------------|------------|
| `edgar_sub_{year}_q{quarter}` | Filing metadata per quarter | ~5,800 |
| `edgar_num_{year}_q{quarter}` | Financial numbers per quarter | ~3.1M |
 
### Master Tables
| Table | Description | Rows |
|-------|-------------|------|
| `edgar_sub_all` | All 28 quarters of filing metadata unified | 192,059 |
| `edgar_num_all` | All 28 quarters of financial numbers unified | 88,170,247 |
 
### Cleaned Tables
| Table | Description | Rows |
|-------|-------------|------|
| `edgar_sub_clean` | Cleaned filing metadata | 192,059 |
| `edgar_num_clean` | Cleaned financial numbers (segments filtered) | 42,890,670 |
 
### Ratio Tables
| Table | Formula | Rows |
|-------|---------|------|
| `ratio_current` | Current Assets / Current Liabilities | 150,347 |
| `ratio_debt_to_equity` | Long Term Debt / Stockholders Equity | 9,662 |
| `ratio_roa` | Net Income / Total Assets | 52,401 |
| `ratio_roe` | Net Income / Stockholders Equity | 49,531 |
| `ratio_gross_margin` | Gross Profit / Revenue | 16,793 |
| `ratio_operating_margin` | Operating Income / Revenue | 29,082 |
| `ratio_debt_ratio` | Total Liabilities / Total Assets | 160,891 |
| `ratio_asset_turnover` | Revenue / Total Assets | 35,181 |
 
### Analytical Tables
| Table | Description | Rows |
|-------|-------------|------|
| `edgar_ratios` | Pivoted wide format financial data | 191,828 |
| `edgar_kpi_unified` | All 8 ratios joined into one table | 150,347 |
| `edgar_kpi_clean` | Outlier-filtered KPI table | 139,696 |
 
## KPIs Analyzed
| KPI | Formula | Measures |
|-----|---------|---------|
| Current Ratio | Current Assets / Current Liabilities | Short-term liquidity |
| Debt Ratio | Total Liabilities / Total Assets | Overall leverage |
| ROA | Net Income / Total Assets | Asset efficiency |
| ROE | Net Income / Stockholders Equity | Equity efficiency |
| Operating Margin | Operating Income / Revenue | Operational efficiency |
| Gross Margin | Gross Profit / Revenue | Production efficiency |
| Asset Turnover | Revenue / Total Assets | Asset utilization |
| Debt to Equity | Long Term Debt / Stockholders Equity | Financial leverage |
 
## Micro Business Questions Answered
| Q | Question |
|---|---------|
| Q1 | How did each KPI trend across Pre-COVID, COVID-Impact and Post-COVID? |
| Q2 | Which sectors were most financially impacted during COVID? |
| Q3 | Which KPIs took longest to recover Post-COVID? |
| Q4 | Which sectors recovered fastest Post-COVID? |
| Q5 | Which KPIs showed most volatility during COVID-Impact? |
| Q6 | How did leverage change during and after COVID? |
| Q7 | Which companies improved vs deteriorated Pre to Post COVID? |
 
## Key Findings
- Current ratio improved 20.4% Post-COVID — strongest recovery KPI
- Debt ratio declined steadily 0.82 → 0.69 — companies deleveraged
- Operating margin not recovered Post-COVID — structural cost pressure
- SIC 5810 (Eating & Drinking) worst hit sector during COVID (ROA delta −0.54)
- SIC 5900 (Retail) fastest recovery Post-COVID (ROA delta +0.52)
- 37.7% of companies improved, 35.7% deteriorated, 28.6% stable Post-COVID
- New leverage cycle beginning in 2024 — debt ratio and D/E rising again
## Analysis Phases
| Phase | Notebook | Tool | Output |
|-------|----------|------|--------|
| 01 Data Ingestion | `data_ingestion` | Python + Spark | 56 raw Delta tables |
| 02 EDA | `eda` | Python + Spark | Master tables + profiling |
| 03 Cleaning & Transformation | `data_cleaning` | Python + Spark SQL | Clean tables + ratio tables |
| 04 Data Aggregation | `data_aggregation` | Python + Spark SQL | KPI unified + insight tables |
| 05 SQL Analysis | `sql_analysis` | SQL (Databricks) | 7 analytical queries |
 
## Data Quality Notes
- Segment-level financial data excluded — consolidated figures only
- Outlier bounds applied: Current Ratio 0–50, Debt Ratio 0–10, ROA −5 to 5
- 1,254 companies with missing SIC codes retained but excluded from sector analysis
- ~7% of observations filtered as extreme outliers
## Project Structure
```
/sec-edgar-financial-analysis/
├── /notebooks/
│   ├── data_ingestion.ipynb
│   ├── eda.ipynb
│   ├── data_cleaning.ipynb
│   ├── data_aggregation.ipynb
│   └── sql_analysis.ipynb
├── /reports/
│   ├── SEC_EDGAR_KPI_Analysis_Report.docx
│   └── SEC_EDGAR_Dashboard.html
└── README.md
```
 
## Timeline
Project completed: June 1, 2026
 
## Author
Meet Saini 
