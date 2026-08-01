# Bank-Loan-Analysis-Dashboard
Bank Loan Analysis Dashboard
# 🏦 Bank Loan Report Dashboard

An interactive Power BI dashboard built to help a bank's lending team monitor loan applications, funding performance, borrower risk, and repayment health across a three-page report: **Summary**, **Overview**, and **Details**.

![Status](https://img.shields.io/badge/status-complete-brightgreen) ![Tool](https://img.shields.io/badge/tool-Power%20BI-yellow) ![Type](https://img.shields.io/badge/type-Banking%20Analytics-blue)

---

## 📌 Project Overview

Banks issue thousands of loans every month and need a fast way to answer three questions:

1. **How much lending activity is happening**, and is it growing or shrinking?
2. **How healthy is the loan book** — how much is "Good" (paying as expected) vs. "Bad" (charged off / defaulted)?
3. **Who are we lending to**, and which segments (state, purpose, employment length, home ownership, loan term) drive volume and risk?

This dashboard answers all three with a Summary page for executives, an Overview page for portfolio analysts, and a Details page for record-level drill-down.

---

## 🗂️ Report Pages

### 1. Summary
Executive snapshot of overall portfolio health and a breakdown of loan status.

- **Good Loan vs. Bad Loan** donut charts (86.2% Good / 13.8% Bad) with Applications, Funded Amount, and Amount Received for each
- **Loan Status table** (Charged Off, Current, Fully Paid, Grand Total) with Total Applications, Total Funded Amount, Total Amount Received, MTD figures, Average Interest Rate, and Average DTI per status

### 2. Overview
Trend and segmentation view of loan applications.

- Total Loan Applications **by Month** (seasonality/growth trend)
- Total Loan Applications **by State** (choropleth map)
- Total Loan Applications **by Term** (36 vs. 60 months)
- Total Loan Applications **by Employment Length**
- Total Loan Applications **by Purpose**
- Total Loan Applications **by Home Ownership**

### 3. Details
A sortable, filterable transaction-level table (loan ID, purpose, home ownership, grade/sub-grade, issue date, funded amount, interest rate, installment, amount received) for auditing individual loans.

All three pages share a common filter panel: **State, Grade, Purpose, Good vs. Bad Loan**.

---

## 📊 Key Metrics (KPI Cards)

| KPI | Value | MTD | MoM |
|---|---|---|---|
| Total Loan Applications | **38.6K** | 1 | -100% |
| Total Funded Amount | **$435.8M** | $5.0K | 0% |
| Total Amount Received | **$473.1M** | $5.9K | 0% |
| Average Interest Rate | **12.0%** | 10.6% | 0.4% |
| Average DTI (Debt-to-Income) | **13.3%** | 13.9% | 0.4% |

**Grand total behind the KPIs:** 38,576 loans → $435,757,075 funded → $473,070,933 received (avg. rate 12.05%, avg. DTI 13.33%).

---

## 🔍 Key Insights

- **Portfolio is largely healthy.** 86.2% of loans (33.2K) are "Good," with $370.2M funded and $435.8M recovered. Only 13.8% (5.3K loans) are classified "Bad," representing $65.5M funded against just $37.3M received — i.e., the bad-loan bucket has recovered less than 60% of what was disbursed.
- **Charged-off loans carry the highest risk profile.** The Charged Off segment (5,333 loans) has the highest average interest rate (13.88%) and DTI (14.00%) of any status, suggesting risk-based pricing is directionally working — but hasn't been enough to prevent losses.
- **Fully Paid dominates volume.** 32,145 loans (83% of the book) are Fully Paid, contributing $351.4M funded and $411.6M received — the primary driver of overall profitability.
- **Strong seasonality in originations.** Applications ramp up steadily from January and spike sharply toward **November** (~21K in the peak month) before dropping off — worth investigating whether this reflects a marketing push, seasonal borrowing behavior (e.g., holiday spending), or a data artifact from a partial December.
- **60-month loans dominate the book** (73.2%, ~28K loans) over 36-month loans (26.8%, ~10K) — longer terms typically mean lower installments but more cumulative interest and more exposure time to default risk.
- **Debt consolidation is the number one borrowing reason** (~18K applications), far ahead of credit cards (~5K), other (~4K), and home improvement (~3K) — indicating the bank's customer base is largely using loans to restructure existing debt rather than fund new purchases.
- **Renters and mortgage-holders make up almost the entire borrower base** (18K RENT, 17K MORTGAGE), with outright homeowners (OWN) a small minority — a segment with less collateral/equity cushion, relevant to risk modeling.
- **Employment tenure skews toward stability**, with "10+ years" the single largest employment-length group (~8.9K applications), which is generally a positive credit-risk signal.
- **California leads state-level volume**, consistent with population-weighted lending patterns.

---

## 🛠️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures, and report authoring
- **DAX** — for MTD/MoM KPI calculations, Good vs. Bad Loan classification, and Average Interest Rate / DTI measures
- **Power Query** — data cleaning and transformation
- Underlying dataset: loan-level lending data (loan ID, purpose, home ownership, grade/sub-grade, term, issue date, funded amount, interest rate, installment, amount received, loan status)

---

## 📁 Suggested Repository Structure

```
bank-loan-report/
├── README.md
├── data/
│   └── financial_loan.csv          # source dataset (or link if data is private)
├── dashboard/
│   └── Bank_Loan_Report.pbix       # Power BI file
├── screenshots/
│   ├── summary.png
│   ├── overview.png
│   └── details.png
└── docs/
    └── dax_measures.md             # documented DAX formulas
```

---

## 🚀 How to Use

1. Clone this repository.
2. Open `Bank_Loan_Report.pbix` in Power BI Desktop (free download from Microsoft).
3. Use the filter panel (State, Grade, Purpose, Good vs. Bad Loan) to slice the data.
4. Navigate between **Summary → Overview → Details** using the left-hand nav buttons.

---

## 💡 Possible Next Steps

- Add a **cohort/vintage analysis** to see how default rates evolve by issue month.
- Build a **risk-adjusted return** measure (interest earned minus charge-offs) per grade/sub-grade.
- Investigate the **November spike** in applications to confirm it's genuine seasonality and not a data-load issue.
- Add **year-over-year** comparisons once multiple years of data are available (currently MoM/MTD only).

---

 📷 Screenshots

Add exported PNGs of each page (Summary, Overview, Details)  and reference them here, e.g.:

Link 1 (Power BI Summary Dashboard ):

![Alt Text](https://github.com/Govag975/Bank-Loan-Analysis/blob/main/Screenshot%202026-08-01%20110142.png)

Link 2 ( Power BI Overview Dashboard) :

![Alt Text](https://github.com/Govag975/Bank-Loan-Analysis/blob/main/Screenshot%202026-08-01%20110130.png)

Link 3 (Power BI Details Dashboard ):

![Alt Text](https://github.com/Govag975/Bank-Loan-Analysis/blob/main/Screenshot%202026-08-01%20110117.png)

Link 4 (MS Excel Summary Dashboard ):

![Alt Text](https://github.com/Govag975/Bank-Loan-Analysis/blob/main/Screenshot%202026-08-01%20110341.png)

Link 5 (MS Excel Overview Dashboard ):

![Alt Text](https://github.com/Govag975/Bank-Loan-Analysis/blob/main/Screenshot%202026-08-01%20110355.png)

---

## 📄 License

license here
![Drivelink](https://drive.google.com/drive/folders/1q135b1Ahlm1I03s3sYHgqNoPZbkqTSVK) if you intend this project to be reused by others.
