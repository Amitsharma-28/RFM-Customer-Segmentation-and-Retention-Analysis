# 📦 Customer Segmentation Analysis | Microsoft Excel
### RFM Analysis — PrintPlus Studios
 
An Excel-based customer segmentation project applying an RFM (Recency, Frequency, Monetary) framework to one year of transaction data to identify high-value customers, detect disengaged segments, and deliver actionable marketing recommendations.
 
---
 
## 📌 Objective
 
PrintPlus Studios generates substantial data from daily transactions and customer interactions, but much of this information had historically been underutilised. This project addresses that gap by answering three key business questions:
 
1. Who are PrintPlus Studios' **best customers**?
2. Which customers should be targeted with a **retention campaign**?
3. Which customers can PrintPlus Studios **safely exclude** from paid campaigns?
All the Excel formulas used for the analysis can be found [here](https://docs.google.com/document/d/11wYtmhPXSS-ClJ5QhHnWWfoReHPZVQd5/edit?usp=sharing&ouid=102165638531054537510&rtpof=true&sd=true).
---
 
## 📂 Dataset
 
The dataset contains **1,000 transaction-level records** covering one full year of customer order history.
 
| Field | Description |
|---|---|
| `OrderID` | Unique identifier for each transaction |
| `CustomerID` | Identifier for the customer who placed the order |
| `OrderDate` | Date the purchase was made |
| `ProductType` | Type of product purchased |
| `OrderValue` | Total monetary value of the order (USD) |
 
---
 
## 🔎 Data Quality Checks
 
Prior to analysis, the following checks were conducted:
 
- Identified duplicate `OrderID` values
- Checked for blanks in critical fields (`OrderDate`, `OrderValue`, `CustomerID`)
- Verified the earliest and latest transaction dates to confirm the accuracy of the analysis window
---
 
## 🧮 Methodology
 
Customers were scored across three RFM dimensions on a scale of **1–5**, producing a combined score out of 15. Scores were assigned using `PERCENTILE.INC`, and customers were grouped into five segments using `IFS` logic based on their total RFM score.
 
| Dimension | Description |
|---|---|
| **Recency (R)** | How recently the customer made a purchase |
| **Frequency (F)** | How often the customer purchases |
| **Monetary (M)** | How much the customer has spent in total |
 
| Segment | RFM Score |
|---|---|
| 🏆 Best Customers | ≥ 13 / 15 |
| 💚 Loyal Customers | 10-12 / 15 |
| 🌱 Potential Loyal Customers | 7-9 / 15 |
| ⚠️ Need Attention | 4–6 / 15 |
| 🔴 At Risk | 3 / 15 |
 
---
 
## 📊 Findings
 
### 🏆 Best Customers — 61 customers (RFM Score ≥ 13)
 
| Metric | Value |
|---|---|
| Avg. days since last purchase | ~48 days |
| Avg. purchases per year | ~6 |
| Avg. spend | $110.88 |
| Share of total revenue | ≈39% |
 
This segment demonstrates strong recency, high purchase frequency, and the highest monetary contribution. Best customers consistently fall within the top percentile tiers across all three RFM dimensions, placing them among the highest contributors to total revenue.
 
---
 
### ⚠️ Need Attention — 57 customers (RFM Score 4–6)
 
| Metric | Value |
|---|---|
| Avg. days since last purchase | ~170 days |
| Avg. purchases per year | ~2 |
| Avg. spend | $23.65 |
| Share of total revenue | ≈8% |
 
This segment has not interacted with the business for a significant period and is trending toward disengagement. Characterised by low purchase frequency and limited spending, the need attention segment is predominantly composed of low-spending customers with limited revenue contribution and an elevated risk of churn.
 
---
 
### 🔴 At Risk — 13 customers (RFM Score 3)
 
| Metric | Value |
|---|---|
| Avg. days since last purchase | ~284 days |
| Avg. purchases per year | ~1 |
| Avg. spend | $10.67 |
| Share of total revenue | ≈0.8% |
 
All 13 customers fall in the bottom 20% across every RFM dimension. With prolonged inactivity, extremely low purchase frequency, and minimal spending, the at risk segment contributes the lowest revenue levels in the dataset and shows a high likelihood of permanent disengagement.
 
---
 
## ✅ Recommendations
 
| Segment | Action | Rationale |
|---|---|---|
| 🏆 Best Customers | Launch a VIP loyalty programme with exclusive benefits (e.g. priority printing, premium templates) | Generates ≈39% of revenue; high repeat-purchase behaviour makes investment in them highly profitable |
| ⚠️ Need Attention | Deploy a re-engagement campaign with a limited-time incentive (e.g. 10% off, free shipping) | Averaged ~2 purchases/year; realistic reactivation opportunity at relatively low cost |
| 🔴 At Risk | Exclude from all paid marketing campaigns | Contributes <1% of revenue with almost no likelihood of reactivation; exclusion prevents marketing waste |
 
---
 
## 🛠️ Tools & Techniques
 
- **Microsoft Excel** — PERCENTILE.INC, IFS, Pivot Tables
- RFM Scoring Framework
- Customer Segmentation
