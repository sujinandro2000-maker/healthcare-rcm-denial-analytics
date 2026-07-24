# healthcare-rcm-denial-analytics
An end-to-end Healthcare Revenue Cycle Management (RCM) analytics project using Python and Power BI to identify claim denial root causes, analyze prior-authorization bottlenecks, and reclaim lost revenue.
# 🏥 Healthcare RCM Claims & Denial Analytics

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811?style=flat&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=flat&logo=pandas&logoColor=white)

## 📋 Project Overview
Revenue Cycle Management (RCM) in healthcare is heavily impacted by claim denials, delayed payments, and prior authorization bottlenecks. This project provides an end-to-end data analytics pipeline that evaluates medical billing claims data to identify root causes of claim rejections, quantify lost revenue, and highlight operational process improvements.

Using **Python (Pandas/Seaborn)** for exploratory data analysis and data transformation alongside **Power BI** for interactive executive dashboarding, this repository demonstrates how data analytics can reclaim trapped revenue for healthcare providers.

---

## 🎯 Key Business Questions Addressed
1. **Financial Impact:** What is our overall denial rate, and how much billed revenue is currently blocked by claim rejections?
2. **Root-Cause Analysis:** Which denial categories (`denial_category`) and reason codes (`denial_reason_code`) contribute the most to lost revenue?
3. **Operational Bottlenecks:** Which provider specialties have the highest rate of missing prior authorizations despite authorization being mandatory?
4. **Payer Performance:** How do denial rates vary across quarters and among different payer types (e.g., Medicare, Commercial)?

---

## 🛠️ Tech Stack & Skills
- **Data Manipulation & Preprocessing:** Python (`pandas`, `numpy`)
- **Data Visualization:** Python (`matplotlib`, `seaborn`), Power BI
- **Database/Query Logic:** SQL principles for aggregation & filtering
- **Domain Focus:** Healthcare Finance, Revenue Cycle Management (RCM), Medical Billing & Coding (CPT / ICD-10)

---

## 📊 Core RCM Metrics Calculated

| Metric | Formula / Logic |
| :--- | :--- |
| **Total Billed Revenue** | $\sum (\text{claim\_amount\_usd})$ |
| **Overall Denial Rate** | $\frac{\text{Count of Denied Claims}}{\text{Total Claims Submitted}} \times 100$ |
| **Total Revenue Lost** | $\sum (\text{claim\_amount\_usd}) \text{ where outcome = 'Denied'}$ |
| **Prior Auth Non-Compliance** | $\text{Claims where } \texttt{prior\_auth\_required} = \text{True AND } \texttt{prior\_auth\_obtained} = \text{False}$ |

---

## 💡 Key Business Insights Discovered
* **Prior Authorization Leakage:** High non-compliance rates were identified in mandatory prior authorization claims, leading to preventable initial denials.
* **Top Revenue Loss Drivers:** A small subset of denial categories (such as missing clinical documentation and authorization failures) accounted for the majority of total denied dollars.
* **Specialty Variance:** Specific specialties showed significantly higher denial rates under commercial payers compared to government payers for similar procedure codes.

---

## 📁 Repository Structure

```text
healthcare-rcm-denial-analytics/
│
├── data/
│   ├── raw_rcm_claims.csv                # Raw claims dataset
│   └── processed_summary_tables/         # Cleaned CSV exports for Power BI
│       ├── rcm_denial_summary.csv
│       ├── rcm_prior_auth_analysis.csv
│       └── rcm_quarterly_trend.csv
│
├── notebooks/
│   └── rcm_exploratory_analysis.ipynb    # Jupyter Notebook with full Python pipeline
│
├── dashboard/
│   └── rcm_executive_dashboard.pbix      # Power BI interactive dashboard file
│
└── README.md                             # Project documentation
