# The Big Picture: Nigeria's 2026 Federal Budget, Decoded

### *"Paying for Yesterday with Tomorrow's Money — Where the Average Nigerian's Money Goes"*

**A Power BI Investigative Data Story | Simulated Client: Channels Television**
**Produced by: Yusuf Shotunde*

---

## 📌 Table of Contents

1. [Project Overview](#-project-overview)
2. [The Brief](#-the-brief)
3. [Data Sources & Methodology](#-data-sources--methodology)
4. [Data Cleaning & Structuring](#-data-cleaning--structuring)
5. [Dashboard Architecture](#-dashboard-architecture)
6. [Page 1: The Big Picture](#page-1-the-big-picture)
7. [Page 2: Where the Money Goes](#page-2-where-the-money-goes)
8. [Page 3: What It Means for Nigerians](#page-3-what-it-means-for-nigerians)
9. [Key Findings](#-key-findings)
10. [Full 2025 vs 2026 Comparison Scorecard](#-full-2025-vs-2026-comparison-scorecard)
11. [Tools & Tech Stack](#-tools--tech-stack)
12. [Limitations & Caveats](#-limitations--caveats)
13. [Recommendations](#-recommendations)
14. [How to Use This Repo](#-how-to-use-this-repo)
15. [Author](#-author)
16. [Acknowledgements & Disclaimer](#-acknowledgements--disclaimer)

---

## 🎯 Project Overview

Every year, the Nigerian Federal Government publishes an Appropriation Bill running into hundreds of pages of line items, codes, and figures that are functionally inaccessible to the average citizen. Yet this single document determines how much is spent on hospitals, schools, roads, security, and — increasingly — the interest on money already borrowed.

This project takes the **2026 Federal Government Budget** (benchmarked against 2025) and translates it into a **3-page interactive Power BI dashboard** and supporting investigative narrative, built for a general audience rather than economists or civil servants.

The guiding question was simple: **if you handed ₦100 of government spending to an ordinary Nigerian and asked "where does this actually go?" — what would the honest answer be?**

---

## 📋 The Brief

We were handed:
- Raw 2025 and 2026 budget figures (no template, no pre-built structure)
- A mandate to identify the *story* inside the numbers, not just report totals
- A requirement to make the findings understandable to a non-technical, general audience
- A simulated client (Channels Television) expecting a prime-time-ready data report

No guided questions were provided. The analytical framing — deficit, debt burden, sectoral allocation, and the human cost of spending choices — was developed entirely by me from first principles.

---

## 🔍 Data Sources & Methodology

| Source | Role |
|---|---|
| **Budget Office of the Federation (BOF)** | Primary source — 2025 & 2026 Appropriation figures |
| **BudgIT** | Cross-verification of sectoral and ministry-level breakdowns |
| **PwC Nigeria Budget Analysis** | Cross-verification of macro figures (deficit, revenue, debt service) |

**Methodology:**
1. Extracted raw appropriation data for 2025 and 2026 fiscal years
2. Cross-checked headline figures (Total Budget, Revenue, Deficit, Debt Service) across all three sources to resolve discrepancies
3. Reconciled ministry-level and statutory transfer line items against the official Appropriation Bill schedule
4. Flagged and documented any figures that could not be independently verified
5. Structured the reconciled data into six analysis-ready CSV files
6. Built relationships between tables in Power BI's data model to enable cross-filtering across Sector, Ministry/Agency, and Year

---

## 🧹 Data Cleaning & Structuring

The raw Appropriation Bill data was not analysis-ready. Key cleaning steps included:

- **Standardizing units** — converting all figures to a consistent ₦ Trillion (and ₦ Billion, where needed) scale across both fiscal years
- **Harmonizing ministry names** — the same ministry/agency is often labeled inconsistently across budget documents (e.g., abbreviations, renamed agencies, merged parastatals); names were standardized to allow accurate 2025-vs-2026 comparison
- **Categorizing budget lines** into the four standard functional heads: **Capital Expenditure, Debt Service, Recurrent (Non-Debt), and Statutory Transfers**
- **Separating debt service** into **Domestic** and **Foreign** components
- **Isolating statutory transfers** (INEC, Niger Delta Development Commission, National Assembly, Judiciary, etc.) into a rankable table
- **Building calculated fields** for YoY % change, share-of-budget %, and per-₦100 allocation breakdowns
- **Validating totals** — ensuring that the sum of functional heads reconciled to the published Total Budget Appropriation figure for both years

**Output:** 6 structured, analysis-ready CSV files covering macro budget summary, functional classification, ministry-level recurrent spend, ministry-level capital spend, statutory transfers, and debt service composition.

---

## 🏗️ Dashboard Architecture

The dashboard is built as a **3-page interactive Power BI report**, with global slicers for **Year (2025/2026)**, **Sector**, and **Ministry/Agency** enabling cross-page filtering.

### Page 1: The Big Picture
*The macro story — how big is the budget, and how is it funded?*

<img width="800" height="445" alt="image" src="https://github.com/user-attachments/assets/21ae1f54-4242-40b3-a66a-28a9d4330631" />

**KPI Cards:**
- Total Budget 2026: **₦58.47 trillion**
- Fiscal Deficit 2026: **₦25.27 trillion**
- Deficit as % of 2026 Budget: **43.22%**
- Debt Service as % of 2026 Budget: **27.21%**
- Deficit YoY Change: **+93.22%**
- Revenue YoY Change: **−20.59%**

**Visuals:**
- *Revenue vs Budget vs Deficit (2025 vs 2026)* — clustered bar chart showing Total Budget rising from ₦55T to ₦58T, Total Revenue **falling** from ₦42T to ₦33T, and the Fiscal Deficit nearly doubling from ₦13T to ₦25T
- *How Every ₦100 of the 2026 Budget Is Allocated* — donut chart: Capital Expenditure 39.7% (₦23T), Debt Service 27.21% (₦16T), Recurrent Non-Debt 26.08% (₦15T), Statutory Transfers 7.01% (₦4T)
- *Main Budget Categories: 2025 vs 2026* — horizontal bar comparison across all functional heads
- *Domestic vs Foreign Debt Service (2025 vs 2026)* — Domestic debt service roughly flat (₦10.4T → ₦10.2T); Foreign debt service declining (₦5.9T → ₦5.4T)

### Page 2: Where the Money Goes
*The institutional story — which ministries and transfers actually receive the money?*

<img width="480" height="271" alt="image" src="https://github.com/user-attachments/assets/3e7e67b6-b92f-4caa-a23e-a7b09d548bb5" />

**KPI Cards:**
- Largest Capital Allocation 2026: **Federal Ministry of Works**
- Total Statutory Transfers 2026: **₦4.10 trillion**
- INEC vs Health Spending Ratio: **4.72×**

**Visuals:**
- *Top 10 Ministries — Recurrent Spending (2025 vs 2026)* — led by Defence, Interior, Health, and Foreign Affairs
- *Top 10 Ministries — Capital Spending (2025 vs 2026)* — led by Power, Finance, Works, Education, and Health
- *Sector Spending Comparison (2025 vs 2026)* — grouped view across Defence & Security, Education, Health, Social Development, and Agriculture & Rural Development
- *Statutory Transfers Ranked (2026)* — a waterfall of transfer beneficiaries from largest (~₦1.01T) down to the smallest (~₦0.07T)

### Page 3: What It Means for Nigerians
*The human story — translating totals into what citizens actually receive and lose*

<img width="480" height="274" alt="image" src="https://github.com/user-attachments/assets/3f25689e-c8c0-43fe-a6ed-21744475f822" />

**KPI Cards:**
- Education Share of 2026 Budget: **3.31%**
- Health Share of 2026 Budget: **3.26%**
- Debt Service vs (Education + Health) Ratio: **4.14×**
- Capital Budget Growth (2025 → 2026): **68.84%**

**Visuals:**
- *Nigeria's Education & Health Budget vs What Is Recommended* — actual allocation percentages plotted against the UNESCO (17.5%) and WHO (15%) international benchmarks
- *Security vs Social Sector Spending (2025 vs 2026)* — Defence & Security spend compared directly against Education, Health, and Agriculture
- *Which Sectors Grew and Which Were Cut (2025–2026, % Change)* — a full ranked bar chart of every sector's YoY percentage movement, from the biggest gainers to the biggest losers
- *2025 vs 2026 Federal Budget — Full Comparison Scorecard* — a complete line-item table (see below) covering every functional budget head

---

## 💡 Key Findings

### 1. The Deficit Nearly Doubled
The 2026 fiscal deficit of ₦25.27 trillion represents a **93% increase** over 2025's ₦13 trillion deficit — driven by revenue that *fell* 20.6% year-on-year even as the total budget grew. In practical terms: **for every ₦100 the government plans to spend, only ₦57 is backed by actual revenue; the remaining ₦43 must be borrowed.**

### 2. Debt Service Now Outranks Development in Priority
₦15.91 trillion — **27.2% of the entire budget** — is committed to servicing existing debt before a single kobo reaches any ministry for actual service delivery. Debt service is effectively the **second-largest line item in the budget**, trailing only capital expenditure.

### 3. Revenue Concentration Risk Remains High
The federal revenue base remains heavily tied to the Federation Account, which is predominantly oil-and-gas funded. This leaves the entire budget plan exposed to a single commodity's price and production volatility.

### 4. Capital Spending Is Up — But Execution Is the Real Test
Capital expenditure grew **68.84%** to ₦23.21 trillion, the highest development allocation in recent memory, with Works, Power, and Agriculture receiving the largest capital increases. However, **Q3 2025 capital budget release stood at only 17.7%** — meaning the historical gap between what is *appropriated* and what is *actually released and spent* is the single biggest threat to this "good news" translating into real infrastructure.

### 5. Education and Health Remain Structurally Underfunded
Education receives 3.31% and Health 3.26% of the 2026 budget — far short of the UNESCO benchmark of 17.5% for education and the WHO benchmark of 15% for health. Debt service alone is **4.14 times larger** than the combined education and health allocation.

### 6. Security Spending Outpaces Social Investment
The security cluster consumes over ₦5 trillion in recurrent spending alone — more than education and health combined — reflecting what the analysis frames as a **political prioritization**, not a resource constraint.

---

## 📊 Full 2025 vs 2026 Comparison Scorecard

| Budget Item | 2025 (₦) | 2026 (₦) | Change (%) | Change (₦) |
|---|---|---|---|---|
| Capital Expenditure | 13,740,000,000,000 | 23,214,347,381,824 | +68.9% | 9,465,347,381,824 |
| Debt Service | 16,271,428,691,845 | 15,908,061,631,857 | −2.2% | −4,178,105,798,199* |
| Deficit Financing (New Borrowings) | 13,000,000,000,000 | 23,521,993,952,171 | +91.0% | 12,193,505,952,171* |
| Fiscal Deficit | 13,000,000,000,000 | 25,270,993,952,171 | +93.2% | 12,193,505,952,171 |
| Recurrent (Non-Debt) | 14,100,000,000,000 | 15,251,038,621,943 | +8.2% | 1,041,038,621,943* |
| Statutory Transfers | 4,057,167,921,000 | 4,097,891,725,375 | +1.0% | 40,591,050,375* |
| **Total Budget Appropriation** | **54,993,700,000,000** | **58,470,000,000,000*** | **+6.3%** | **3,384,993,999,375*** |

> ⚠️ **Note:** This table reproduces the dashboard's scorecard visual as captured. Some figures marked with an asterisk (\*) appear inconsistent with the headline totals shown elsewhere in the dashboard (e.g., a ₦58.47T headline Total Budget vs. the ~₦58.36T implied by summing line items) and should be re-validated against the original CSVs / Appropriation Bill before this table is treated as final in any published report. See [Limitations & Caveats](#-limitations--caveats).

---

## 🛠️ Tools & Tech Stack

| Tool | Purpose |
|---|---|
| **Microsoft Power BI Desktop** | Data modeling, DAX measures, and 3-page interactive dashboard build |
| **Power Query (M)** | Data cleaning, transformation, and shaping of raw budget data |
| **Excel / CSV** | Intermediate structuring of the 6 analysis-ready datasets |
| **DAX** | Calculated KPIs — YoY % change, share-of-budget %, per-₦100 allocation |
| **GitHub** | Version control, dataset hosting, and documentation |

---

## ⚠️ Limitations & Caveats

- **Simulated engagement**: This was produced as a simulation exercise; it is not an official Channels Television publication.
- **Source reconciliation**: Minor figure discrepancies exist between the Budget Office, BudgIT, and PwC sources on some sub-line items; where these could not be fully reconciled, the most frequently corroborated figure was used and should be independently re-verified before external publication.
- **Rounding**: Dashboard visuals display rounded figures (to the nearest ₦T or ₦B); the underlying CSVs retain full precision.
- **Execution vs. appropriation**: All capital expenditure figures represent *appropriated* (budgeted) amounts, not *released* or *actually spent* amounts. The Q3 2025 release rate of 17.7% is cited as important context but is not reflected in the headline capital expenditure KPIs.
- **Ratio metrics** (e.g., INEC vs. Health, Debt vs. Education+Health) are illustrative comparative devices designed for public communication, not formal budgetary classifications.

---

## 🧭 Recommendations

1. **Publish a real-time capital release tracker** alongside the appropriation dashboard, so citizens can compare *budgeted* vs. *actually released* capital spending quarter by quarter.
2. **Diversify revenue reporting** to make the Federation Account's oil/gas dependency more visible to the public in every budget cycle, not just in special reports.
3. **Benchmark education and health allocations publicly** against UNESCO/WHO standards every year, to keep the funding gap in the national conversation.
4. **Reconcile debt service reporting** across BOF, BudgIT, and PwC to eliminate the kind of figure discrepancies flagged in this project's scorecard.
5. **Push for a citizen-facing "budget in plain language" release** from the Budget Office itself, reducing reliance on third-party civic tech translations like this one.

---

## 📂 How to Use This Repo

```
├── data/
│   ├── 01_macro_budget_summary.csv
│   ├── 02_functional_classification.csv
│   ├── 03_ministry_recurrent_spend.csv
│   ├── 04_ministry_capital_spend.csv
│   ├── 05_statutory_transfers.csv
│   └── 06_debt_service_composition.csv
├── dashboard/
│   └── the_big_picture_2026.pbix
├── report/
│   └── investigative_story_report.pdf
└── README.md
```

1. Clone the repository
2. Open `dashboard/the_big_picture_2026.pbix` in **Power BI Desktop** (free download from Microsoft)
3. Use the **Year**, **Sector**, and **Ministry/Agency** slicers on any page to filter across all three report pages
4. Raw datasets are available in `/data` for independent analysis or re-use (please credit The Data Refinery and cite the original sources: Budget Office of the Federation, BudgIT, PwC Nigeria)

---
## 👤 Author

*(Yusuf Shotunde, LinkedIn: www.linkedin.com/in/yusuf-shotunde / GitHub: https://github.com/Yusinho/ / CV: https://github.com/Yusinho/my-portfolio/blob/main/Yusuf_Lanre_Shotunde_CV.pdf )*

---

## 🙏 Acknowledgements & Disclaimer

Data sourced and cross-verified from the **Budget Office of the Federation**, **BudgIT**, and **PwC Nigeria**. This project was produced as a simulated investigative data journalism exercise for a fictional Channels Television engagement, and is intended for portfolio, educational, and civic-tech demonstration purposes. It does not represent an official publication of Channels Television, the Budget Office of the Federation, or the Federal Government of Nigeria. All figures should be independently verified against the official 2026 Appropriation Bill before use in any formal reporting or decision-making context.

---

👇 Dashboard snapshot and link below:.
https://lnkd.in/euyftYQi



