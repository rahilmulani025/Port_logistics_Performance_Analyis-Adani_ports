# 🚢 Adani Ports & Renewable Energy — Statistical & BI Analysis

<div align="center">

![Project Banner](https://img.shields.io/badge/Project-Port%20Logistics%20%26%20BI%20Analysis-1F3864?style=for-the-badge&logo=data:image/png;base64,)

[![Excel](https://img.shields.io/badge/Microsoft%20Excel-Statistical%20Modeling-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://www.microsoft.com/excel)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![Status](https://img.shields.io/badge/Status-Completed-2E4C8C?style=for-the-badge)](https://github.com)
[![Internship](https://img.shields.io/badge/UV%20Netware-Internship%20Project-E2EFDA?style=for-the-badge)](https://uvnetware.com)

<br/>

> **A full-scale statistical and business intelligence analysis of India's largest port operator —**  
> **covering 450 MMT of cargo, ₹860 Billion in revenue, and 15.5 GW of renewable energy capacity.**

<br/>

| 📦 Total Cargo | 💰 Total Revenue | ⚡ Renewable Capacity | 🏭 Ports Analyzed |
|:-:|:-:|:-:|:-:|
| **450 MMT** | **₹860 Billion** | **15.5 GW** | **10 Ports** |

</div>

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Key Findings](#-key-findings)
- [Project Structure](#-project-structure)
- [Datasets Used](#-datasets-used)
- [Statistical Analysis](#-statistical-analysis)
- [Power BI Dashboard](#-power-bi-dashboard)
- [12 Analytical Questions](#-12-analytical-questions--answers)
- [Tools & Technologies](#-tools--technologies)
- [How to Use](#-how-to-use)
- [Strategic Conclusion](#-strategic-conclusion)

---

## 🎯 About the Project

This project was developed during my internship at **UV Netware** (Reference: ADAFI15665) as a comprehensive statistical and business intelligence study of **Adani Ports and Special Economic Zone (APSEZ)** — India's largest port operator with a 27% national cargo market share.

The objective was to build an Excel-based statistical model and Power BI dashboard to analyze port logistics performance, renewable energy efficiency, and regional revenue distribution — and answer 12 strategic business questions for CFO-level review.

---

## 🔍 Key Findings

```
╔══════════════════════════════════════════════════════════════════╗
║  📍 Mundra Port = 52.17% of total listed cargo (concentration risk) ║
║  📈 FY2026 Forecast = 506–514 MMT  |  FY2027 = 562–570 MMT        ║
║  💡 North Region = ₹2.40B/MMT (highest revenue efficiency)         ║
║  📊 ANOVA: F = 32.48, p = 0.0000789 → regions differ significantly ║
║  🎯 P(cargo > 43 MMT) = 5.32% → once every ~19 months             ║
║  🏭 Industrial customers drive 70% of cargo (χ² = 21.38, p<0.001) ║
╚══════════════════════════════════════════════════════════════════╝
```

---

## 📁 Project Structure

```
adani-ports-analytics/
│
├── 📊 Excel Model/
│   └── ADAFI15665_Master_Data_FINAL.xlsx
│       ├── Sheet 1 — Raw Data (6 datasets)
│       ├── Sheet 2 — Descriptive Statistics
│       ├── Sheet 3 — ANOVA Analysis
│       ├── Sheet 4 — Chi-Square Test
│       ├── Sheet 5 — Normal Distribution
│       ├── Sheet 6 — Forecasting (Annual + Monthly)
│       ├── Sheet 7 — BI Dataset (Power BI Source)
│       └── Sheet 8 — Final Output Summary
│
├── 📈 Power BI/
│   └── ADAFI15665_Dashboard.pbix
│
├── 📄 Report/
│   └── ADAFI15665_Final_Report.pdf
│
└── 📝 README.md
```

---

## 📦 Datasets Used

| # | Dataset | Description | Source |
|---|---------|-------------|--------|
| 1 | **Annual Cargo** | FY2023–FY2025 total cargo (339→420→450 MMT) | Adani Ports Annual Report FY24 |
| 2 | **Port-Level Cargo** | 10 ports with FY24 cargo volumes | Annual Report + ITLN |
| 3 | **Monthly Cargo** | 12 exact monthly values (Jan–Dec) | Manager-provided (Q4 clarification) |
| 4 | **Regional Data** | 4 regions — Cargo, Revenue, Energy | Problem brief |
| 5 | **Energy Mix** | Solar 11,005 MW / Wind 1,977 MW / Hybrid 2,556 MW | Adani Green Energy press release |
| 6 | **Customer Segment** | Industrial vs Retail × Bulk vs Container | Problem brief |

### 📅 Monthly Cargo Data (Manager-Provided Exact Values)

| Jan | Feb | Mar | Apr | May | Jun | Jul | Aug | Sep | Oct | Nov | Dec |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 38.6 | 36.4 | 40.1 | 35.9 | 41.8 | 39.7 | 37.5 | **42.2** | 39.4 | 41.0 | 40.5 | 41.9 |

> All values in MMT. Total = 475 MMT. Peak = August (42.2). Trough = April (35.9).

---

## 📐 Statistical Analysis

### 1️⃣ Descriptive Statistics

| Statistic | Value |
|-----------|-------|
| Mean (μ) | **39.58 MMT** |
| Standard Deviation (σ) | **2.117 MMT** |
| Variance | 4.482 |
| Minimum | 35.9 MMT (April) |
| Maximum | 42.2 MMT (August) |
| Range | 6.3 MMT |
| Count (n) | 12 months |

---

### 2️⃣ Normal Distribution Analysis

```
Test Value (x) = 43 MMT

Z-Score  = (43 − 39.58) / 2.117  =  +1.614

P(X ≤ 43)  =  94.68%    ← NORMDIST(43, μ, σ, TRUE)
P(X > 43)  =   5.32%    ← 1 − NORMDIST(43, μ, σ, TRUE)

Interpretation: There is a 5.32% probability (~1 in 19 months)
that cargo will exceed 43 MMT in any given month.
```

---

### 3️⃣ ANOVA — Single Factor

**Hypothesis:**
- **H0:** Regional differences do NOT significantly affect cargo throughput
- **H1:** Regional differences DO significantly affect cargo throughput

| Source | SS | df | MS | F | p-value | F Critical |
|--------|----|----|-----|------|---------|-----------|
| **Between Groups** | 30,519 | 3 | 10,173 | **32.48** | **0.0000789** | 4.07 |
| Within Groups | 2,505 | 8 | 313 | — | — | — |
| Total | 33,025 | 11 | — | — | — | — |

> ✅ **Decision: REJECT H0** — p-value (0.0000789) < α (0.05). Regional differences are statistically significant at 99.99% confidence.

---

### 4️⃣ Chi-Square Test

**Hypothesis:**
- **H0:** Customer type does NOT influence cargo category
- **H1:** Customer type DOES influence cargo category

**Observed Frequencies:**

| Customer Type | Bulk Cargo | Container Cargo | Total |
|---------------|-----------|----------------|-------|
| Industrial | 240 (69%) | 110 (31%) | 350 |
| Retail | 70 (47%) | 80 (53%) | 150 |
| **Total** | **310** | **190** | **500** |

```
χ² Statistic  =  21.3841
Degrees of Freedom  =  1
Critical Value (α=0.05)  =  3.841
p-value  ≈  0.0000038
```

> ✅ **Decision: REJECT H0** — Customer type very significantly influences cargo category (χ² >> critical value).

---

### 5️⃣ Forecasting — FORECAST.LINEAR

**Annual Forecast:**

| Year | Actual | Forecast | ±10% Range |
|------|--------|----------|-----------|
| FY2023 | 339 MMT | — | — |
| FY2024 | 420 MMT | — | — |
| FY2025 | 450 MMT | — | — |
| **FY2026** | — | **~506–514 MMT** | 463–565 |
| **FY2027** | — | **~562–570 MMT** | 506–626 |

> Management guidance for FY2026: 505–515 MMT ✅ (matches model)

**Monthly 3-Month Forecast:**

| Month | Period (x) | Forecast |
|-------|-----------|---------|
| January 2026 | 13 | **41.77 MMT** |
| February 2026 | 14 | **42.10 MMT** |
| March 2026 | 15 | **42.44 MMT** |

---

## 📊 Power BI Dashboard

The dashboard was built using **Sheet 7 (BI Dataset)** as the single source of truth.

### Charts Built

| # | Chart | Type | Key Insight |
|---|-------|------|-------------|
| 1 | Cargo Throughput by Port | Clustered Bar | Mundra dominates at 52% |
| 2 | Revenue by Region | Horizontal Bar | West highest total, North highest per MMT |
| 3 | Energy Capacity Mix | Donut | Solar = 70.8% of portfolio |
| 4 | Monthly Cargo Trend | Line | Peak: Aug, May, Dec |
| 5 | Customer Cargo Distribution | Stacked Bar | Industrial = 70% of volume |

### KPI Cards

```
┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐
│  Total Cargo        │  │  Renewable Capacity  │  │  Total Revenue      │
│    450 MMT          │  │    15.5 GW           │  │    ₹860 Billion     │
└─────────────────────┘  └─────────────────────┘  └─────────────────────┘
```

### Statistical Results Panel
The dashboard includes a dedicated statistical insights section displaying:
- ANOVA p-value and F-statistic
- Chi-Square statistic and decision
- Normal distribution exceedance probability

---

## ❓ 12 Analytical Questions & Answers

<details>
<summary><b>Q1 — Annual Cargo Forecast FY2026 & FY2027</b></summary>

Using FORECAST.LINEAR on FY2023–FY2025 data (slope = 55.5 MMT/year):
- **FY2026 = 514 MMT** | FY2027 = 569.5 MMT
- Management guidance (505–515 MMT) validates the model

</details>

<details>
<summary><b>Q2 — Monthly 3-Month Time-Series Forecast</b></summary>

FORECAST.LINEAR on 12-month exact dataset (slope = +0.336 MMT/month):
- **January 2026 = 41.77 MMT**
- **February 2026 = 42.10 MMT**
- **March 2026 = 42.44 MMT**

All three months exceed the current annual mean of 39.58 MMT.

</details>

<details>
<summary><b>Q3 — ANOVA: Do Regions Differ Significantly?</b></summary>

F = 32.48 >> F-critical (4.07) | p = 0.0000789 < 0.05
**REJECT H0** — Regional differences are real and structural at 99.99% confidence.

</details>

<details>
<summary><b>Q4 — Port-Level Contribution Percentages</b></summary>

Total (5 ports) = 345 MMT

| Port | MMT | % |
|------|-----|---|
| Mundra | 180 | **52.17%** |
| Krishnapatnam | 59 | 17.10% |
| Dhamra | 43 | 12.46% |
| Gangavaram | 37 | 10.72% |
| Hazira | 26 | 7.54% |

</details>

<details>
<summary><b>Q5 — Capacity Planning for FY2026 & FY2027</b></summary>

Avg growth = (450−339)/2 = 55.5 MMT/year
- **FY2026 = 506 MMT** (+56 MMT capacity needed)
- **FY2027 = 562 MMT** (+56 MMT capacity needed)
- Current capacity (627 MMT) approaches saturation by FY2028

</details>

<details>
<summary><b>Q6 — Peak Months and Operational Preparedness</b></summary>

**Peak:** August (42.2), December (41.9), May (41.8), October (41.0), November (40.5)
**Trough:** April (35.9), February (36.4)

Schedule maintenance in Feb/Apr. Maximum readiness in Aug/May/Dec.

</details>

<details>
<summary><b>Q7 — Probability of Exceeding 43 MMT and Strategy</b></summary>

Z = 1.614 | **P(X > 43) = 5.32%** (~once every 19 months)

Strategy: Activate surge protocol when tracking crosses 40.5 MMT (90th percentile).

</details>

<details>
<summary><b>Q8 — Improving Energy Efficiency (70–72%)</b></summary>

1. Predictive AI maintenance → reduce downtime to <1.5%
2. Smart grid optimization → cut transmission losses
3. Hybrid portfolio scheduling → target 55–60% capacity factor
4. Automated solar panel cleaning → prevent 5% soiling loss

Moving 71% → 73% generates ~2.7 TWh additional annual energy.

</details>

<details>
<summary><b>Q9 — Three Strategic Priorities (5 Years)</b></summary>

1. **Expand capacity** — 55–60 MMT/year to prevent FY2028 saturation
2. **Grow North region** — 50 → 90 MMT (highest revenue efficiency at ₹2.40B/MMT)
3. **Scale renewables to 20 GW** — energy independence + green hydrogen at Mundra SEZ

</details>

<details>
<summary><b>Q10 — Highest Revenue Efficiency Region</b></summary>

| Region | Revenue/MMT |
|--------|------------|
| West | ₹1.75B |
| East | ₹1.91B |
| South | ₹2.00B |
| **North** | **₹2.40B ← HIGHEST** |

**Action:** Prioritize North capex — 37% more revenue per tonne than West.

</details>

<details>
<summary><b>Q11 — Cost Optimization Across Regions</b></summary>

Universal lever: Replace diesel equipment with electric (powered by APSEZ's 15.5 GW renewables) → 8–12% cost reduction per tonne across all regions.

</details>

<details>
<summary><b>Q12 — Customer Segment to Prioritize</b></summary>

χ² = 21.38, p < 0.001 — **Industrial customers statistically confirmed as primary driver.**

Industrial: 70% of volume, 69% bulk preference → aligns with APSEZ's bulk infrastructure.
**Prioritize: Industrial & Energy sector** (steel, power, oil & gas, cement, exporters).

</details>

---

## 🛠 Tools & Technologies

<div align="center">

| Tool | Purpose | Details |
|------|---------|---------|
| ![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white) **Microsoft Excel** | Statistical Modeling | Data Analysis ToolPak, NORMDIST, FORECAST.LINEAR, CHIDIST |
| ![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black) **Power BI Desktop** | BI Dashboard | 5 charts, 3 KPI cards, statistical results panel |
| 📊 **Statistical Methods** | Analysis | ANOVA, Chi-Square, Normal Distribution, Descriptive Stats |
| 📄 **PDF (ReportLab)** | Report Generation | 12-question analytical report |

</div>

**Excel Functions Used:**
```excel
=NORMDIST()        → Normal distribution probability
=NORMINV()         → Inverse normal (percentile)
=CHIDIST()         → Chi-square p-value
=FORECAST()        → Linear time-series forecast
=STDEV()           → Sample standard deviation
=AVERAGE()         → Mean calculation
=VAR()             → Variance
=SKEW()            → Distribution skewness
=KURT()            → Distribution kurtosis
Data Analysis ToolPak → ANOVA Single Factor, Descriptive Statistics
```

---

## 🚀 How to Use

### Excel Model
```
1. Open ADAFI15665_Master_Data_FINAL.xlsx
2. Enable editing and macros if prompted
3. Navigate sheets using the tab bar at the bottom
4. All formulas are live — changing Sheet 1 data
   automatically updates all downstream sheets
```

### Power BI Dashboard
```
1. Open ADAFI15665_Dashboard.pbix in Power BI Desktop
2. If prompted, refresh data source → point to Sheet 7
   of the Excel file (7_BI_Dataset)
3. All visuals will auto-populate from the Excel source
```

### Color Code Reference (Excel)
```
🔵 Blue text  = Hardcoded input values
⚫ Black text = Formula / calculated values
🟢 Green text = Cross-sheet links
```

---

## 📈 Regional Performance Summary

```
Revenue Efficiency (₹B per MMT)

North  ████████████████████████  ₹2.40B  ← HIGHEST
South  ████████████████████      ₹2.00B
East   ███████████████████       ₹1.91B
West   █████████████████         ₹1.75B  ← BASELINE
```

```
Cargo Volume by Region (MMT)

West   ████████████████████████████████████████  200 MMT
East   ██████████████████████                    110 MMT
South  ██████████████████                         90 MMT
North  ██████████                                 50 MMT
```

> **Key Insight:** West has the most volume but the worst efficiency.  
> North has the least volume but the best efficiency.  
> **→ Grow North. That's where the value is.**

---

## 🎯 Strategic Conclusion

> *APSEZ is not merely growing in volume — it is building the logistics backbone of India's industrial future. The statistical evidence confirms structural regional performance gaps, customer segmentation patterns, and a throughput trajectory approaching capacity limits by FY2028. The path to sustained profitability runs through three priorities: East coast expansion to reduce Mundra concentration, North region development to capture premium revenue efficiency, and renewable energy scaling to 20 GW for energy independence.*

---

## 👤 Author

**Internship Project — UV Netware**
Reference: ADAFI15665 | March 2026
Author And Analysis Done by : Rahil Mulani
Reviewed by: Raghav Shah, CFO — UV Netware

---

## 📄 License

This project was created as part of an internship engagement at UV Netware. All data references are from publicly available Adani Ports Annual Reports and official press releases.

---

<div align="center">

**⭐ If you found this project useful, consider giving it a star!**

<p align="center">
  <a href="https://linkedin.com/in/rahil-rashid-mulani"> <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /> </a>
  <a href="mailto:rahil.mulani.contact@gmail.com"> <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /> </a>
  <a href="https://github.com/rahilmulani025"> <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" /> </a>
</p>
</div>
