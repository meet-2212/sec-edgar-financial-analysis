# SEC EDGAR Financial Ratio Analysis

## Overview
This project investigates which financial ratios derived from SEC EDGAR 
filings are the strongest leading indicators of abnormal stock price 
movements in the 30/60/90 days following a filing date — and whether 
these signals vary by industry sector. The analysis spans pre-COVID, 
COVID impact, and post-COVID recovery periods to identify structural 
shifts in ratio predictability across market cycles and determine 
whether COVID fundamentally changed which indicators matter most.

## Business Question
**"Which financial ratios derived from SEC EDGAR filings are the strongest 
leading indicators of abnormal stock price movements in the 30/60/90 days 
following a filing date — do these signals vary by industry sector — and 
did COVID-19 fundamentally alter which financial indicators serve as 
reliable predictors of stock price behavior?"**

## Target Audience
- Asset Management Firms
- Trading & Hedge Funds
- Real Estate Firms & REITs
- Credit & Risk Analysts

## Tech Stack
- **Cloud Platform:** Databricks
- **Languages:** Python, SQL
- **Data Sources:** SEC EDGAR DERA Financial Statement Data Sets, Yahoo Finance
- **Visualization:** Power BI
- **Version Control:** GitHub

## Data Coverage
- **SEC EDGAR filings:** Q1 2018 — Q1 2025 (29 quarters)
- **Stock price windows:** 30/60/90 days post filing date
- **Period Labels:**
  - Pre-COVID: Q1 2018 — Q4 2019 (8 quarters)
  - COVID Impact: Q1 2020 — Q2 2020 (2 quarters)
  - Post-COVID Recovery: Q3 2020 — Q1 2025 (19 quarters)

## Analysis Phases
| Phase | Description | Tool |
|-------|-------------|------|
| 01 Data Ingestion | Bulk download EDGAR + stock price data | Python |
| 02 Exploration | Dataset profiling, micro business questions | Python + Excel |
| 03 Cleaning & Validation | Handle nulls, outliers, type fixes | Python + Excel |
| 04 SQL Analysis | Ratio computation, correlation, sector breakdown | SQL (Databricks) |
| 05 Insights & Reporting | Findings narrative, visualizations | Power BI |

## Key Financial Ratios
- Price-to-Earnings (P/E)
- Price-to-Book (P/B)
- Debt-to-Equity
- Current Ratio
- Return on Equity (ROE)
- Return on Assets (ROA)
- Operating Margin
- EPS Surprise

## Research Angles
- Which ratios were strongest predictors pre-COVID?
- Did COVID disrupt the predictive power of traditional financial ratios?
- Which ratios emerged as stronger or weaker signals post-COVID?
- Do these shifts vary by industry sector (Tech, REITs, Healthcare, Energy)?

## Timeline
Project completed by May 31, 2026

## Author
Meet | Data Engineer & Analyst
