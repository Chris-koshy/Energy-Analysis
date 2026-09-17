# Dubai Energy Consumption Analysis (2008-2025)

Analysis of 18 years of DEWA energy data to identify consumption efficiency trends, sector shifts, and forecast future demand against UAE's Net Zero 2050 target.

## Overview
This project analyzes energy consumption across Dubai's residential, commercial, industrial, and other sectors from 2008 to 2025. Rather than just tracking total demand growth, the analysis separates raw consumption growth from per-customer efficiency, so it's clear whether rising demand comes from more customers or from each customer using more power.

## Dataset
**Source:** Dubai Statistics Center / DEWA, via data.dubai ("Total Energy Required and Consumed by Type of Consumption")

Fields:
- Year (2008-2025)
- Number of customers, by sector (residential, commercial, industrial, other)
- Energy consumed (GWh), by sector
- Total energy requirement (GWh)
- Power station and desalination auxiliary load

## Analysis

**Sector share shift**
Tracks how residential, commercial, industrial, and other consumption shares changed from 2008 to 2025, reflecting Dubai's economic diversification over that period.

**Per-customer efficiency trend**
Divides energy consumed by customer count for each sector, year over year, to separate genuine efficiency gains from growth in the customer base.

**Anomaly detection**
Flags years where a sector's year-over-year change is statistically unusual (beyond 1.5 standard deviations from that sector's own average), which surfaces the 2020 COVID-19 disruption without hardcoding the search to that year.

**Demand forecast**
A linear trend fit on 18 years of total energy requirement, extended to 2030, framed as a directional floor estimate rather than a precise prediction.

## Key Findings
- Commercial consumption grew from 43% to 53% of total energy use between 2008 and 2025, while residential rose only slightly and "other" fell sharply, reflecting growth driven more by business and tourism infrastructure than by population alone.
- Per-customer consumption fell in residential (-22.8%), industrial (-33.7%), and other (-83.1%), showing real efficiency gains. Commercial is the exception, rising 29.3% per customer, making it the clearest target for future efficiency programs.
- Commercial and industrial consumption both dropped in 2020, consistent with the COVID-19 disruption, and both were flagged automatically by the anomaly detection.
- The linear forecast puts 2030 demand at roughly 68,100 GWh, an 8.7% increase over 2025. This is a floor estimate, since it doesn't account for EV adoption or major new developments.

## Files
- `energy_analysis.ipynb` — full analysis in Python (pandas, matplotlib), with all charts and findings
- `Energy_Dashboard.xlsx` — the same analysis in Excel, built with live formulas so it recalculates if new years are added, plus three built-in charts

## Technologies Used
- Python 3, Jupyter Notebook
- Pandas, NumPy — data reshaping and calculations
- Matplotlib — visualization
- Excel (openpyxl-built) — formula-driven dashboard version

## Possible Next Steps
- Compare the 2030 forecast against DEWA's published clean energy capacity targets, rather than treating Net Zero 2050 as a general frame
- Add DEWA's water consumption dataset to compare electricity and water efficiency trends side by side
- Normalize residential consumption per capita (using population data) instead of per customer, since household size varies
