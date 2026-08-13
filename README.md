# Where Has the Money Gone? U.S. Industry Pay & Employment, 1990–2025

A long-run analysis of how employment, wages, and labor income have shifted across major U.S. industries.

This project is part of the **American Economic Data Repository (AEDR)**, a public economic research repository designed to organize, validate, and analyze long-run U.S. economic data.

## Project Overview

The central question behind this analysis is:

> **Where have the gains in wages, employment, and economic opportunity gone across the U.S. labor market?**

Using **BLS Quarterly Census of Employment and Wages (QCEW)** data from 1990–2025, the analysis establishes a national baseline across major 2-digit NAICS sectors and examines:

- Employment growth and changes in industry employment share
- Nominal and inflation-adjusted average annual pay
- Changes in each industry's share of national wages
- Divergence between employment-share and wage-share changes
- Periods of unusually large structural change

The purpose of the baseline is to identify which industries and periods warrant deeper investigation rather than beginning with a predetermined explanation.

---

## Data & Methodology


A major component of the project was **building the analytical data environment itself**.

<img width="2558" height="1377" alt="SQLite-AEDR_Detailed_Labor_Market" src="https://github.com/user-attachments/assets/61f3b18c-2722-4505-8c5f-9d67acd0262f" />

Historical public datasets were sourced, compiled, standardized, and validated within the AEDR research database. The underlying labor database incorporates QCEW, OEWS, industry classifications, geographic reference data, and supporting economic indicators.

The general workflow was:

**Public Data → SQLite Research Database → Validation & Audit → Analytical Views → Parquet → Python / DuckDB Analysis**

The QCEW source data underwent extensive validation for schema consistency, observation grain, duplicate records, historical coverage, industry classifications, ownership structure, missing or suppressed observations, and internal consistency.

Validated analytical views were then exported to **Parquet** for efficient analysis in Python and DuckDB.

Supporting documentation in this repository contains the detailed database architecture, validation process, methodological decisions, and audit history.

---

## Key Findings

### Real Pay Growth Was Positive, but Highly Uneven

<img width="1583" height="999" alt="Real Average Annual Pay Growth by Industry, 1990-2025" src="https://github.com/user-attachments/assets/a67f811a-3d93-42ba-a661-8848e96da95e" />


After adjusting average annual pay to **constant 2025 dollars using CPI-U**, every comparable major industry showed positive real-pay growth over the full period—but the magnitude varied substantially.

Median real average annual pay growth was approximately **39.8%**.

Some of the strongest increases occurred in:

- **Information:** +139.5%
- **Finance & Insurance:** +99.1%
- **Management of Companies & Enterprises:** +69.6%
- **Professional, Scientific & Technical Services:** +56.8%
- **Real Estate & Rental & Leasing:** +55.1%

At the lower end:

- **Transportation & Warehousing:** +3.3%
- **Retail Trade:** +13.5%
- **Educational Services:** +15.3%
- **Health Care & Social Assistance:** +19.8%

The long-run story is therefore less about a universal decline in real pay and more about **large differences in which industries captured improvements in purchasing power**.

---

### Employment Has Been Continuously Redistributed Across Industries

<img width="1398" height="593" alt="Annual Redistribution of U S Employment Across Industries, 1991-2025" src="https://github.com/user-attachments/assets/4caa6eeb-be07-4c29-ad83-0a5ea623c262" />


The industrial composition of U.S. employment changed throughout the period.

Median annual redistribution across major industries was approximately **0.65 percentage points**, but periods of economic disruption produced substantially larger movements.

Notable years included:

- **1991:** 1.32 pp
- **2002:** 1.29 pp
- **2009:** 2.07 pp
- **2020:** 2.38 pp
- **2022:** 1.21 pp

The largest movement occurred in **2020**, while the Great Recession also produced unusually large changes.

This suggests that structural change in employment is generally gradual but can accelerate sharply during major economic disruptions.

---

### Employment Share and Wage Share Do Not Always Move Together

<img width="1394" height="898" alt="Largest Annual Industry Wage-Share vs  Employment-Share Divergences, 1991-2025" src="https://github.com/user-attachments/assets/a7dc0e4e-498f-4ad0-ab74-2f65f1c02d83" />


Changes in an industry's share of national employment were also compared with changes in its share of national wages.

Several of the largest divergences occurred in **Finance & Insurance, Professional/Scientific/Technical Services, Manufacturing, Accommodation & Food Services, and Health Care & Social Assistance**.

These cases show that changes in employment alone do not fully describe how labor income is being redistributed. An industry can experience relatively modest changes in employment share while capturing a much larger change in national wage share—or the reverse.

These divergences provide specific industries and historical periods for deeper investigation.

---

## Overall Result

The evidence does not point to a uniform deterioration across the U.S. industry structure.

Instead, the 1990–2025 baseline shows **uneven participation in economic gains**.

Real pay increased across the comparable major industries, but the size of those gains differed dramatically. Employment also shifted among industries over time, while changes in employment share did not always correspond proportionally with changes in wage share.

The next stage of the broader research can use these results to move below the national sector level and investigate **which industries, occupations, ownership categories, and geographic areas account for those differences**.

---

## Repository Contents

| File | Description |
|---|---|
| `AEDR_QCEW_Analytical_v1_Public.ipynb` | Reproducible Python/DuckDB analytical notebook |
| `AEDR_QCEW_Audit_Engineering_log.pdf` | Chronological data-validation and engineering record |
| `AEDR_Detailed_Labor_Database_Technical_Reference.pdf` | Technical reference for the underlying labor database |
| `AEDR_Where_Has_the_Money_Gone_Framework.pdf` | Research and analytical framework |
| `Scope_of_Work_Where_Has_the_Money_Gone.pdf` | Project scope, objectives, workflow, and deliverables |

---

## Reproducibility

The analytical Parquet datasets are too large to store directly in this GitHub repository and are instead hosted publicly on **Kaggle**.

The notebook retrieves the required datasets programmatically using `kagglehub`, eliminating machine-specific local file paths.

Core tools used in the project include:

**Python · pandas · DuckDB · SQL · SQLite · Parquet · Jupyter · Kaggle · Matplotlib**

Run `AEDR_QCEW_Analytical_v1_Public.ipynb` from top to bottom to reproduce the published analysis.

---

## Data Sources

Primary sources include:

- U.S. Bureau of Labor Statistics — **Quarterly Census of Employment and Wages (QCEW)**
- U.S. Bureau of Labor Statistics — **Occupational Employment and Wage Statistics (OEWS)**
- U.S. Bureau of Labor Statistics — **Consumer Price Index (CPI-U)**
- **Federal Reserve Economic Data (FRED)**
- NAICS and geographic reference resources

---

## American Economic Data Repository

This project represents the labor-market component of the broader **American Economic Data Repository (AEDR)**.

AEDR is being developed as a reusable public economic research repository supporting a broader investigation into wages, inflation, housing, employment, and the affordability of the American Dream.

The guiding principle is a reproducible path from:

**Source → Validation → Transformation → Analysis → Conclusion**

---

## Contact 

[LinkedIn](https://linkedin.com/in/matthias-benitez-81a8a7197)

[Kaggle](https://www.kaggle.com/matthiasbenitez)

[Mbenitezzz33@outlook.com](mailto:Mbenitezzz33@outlook.com)
