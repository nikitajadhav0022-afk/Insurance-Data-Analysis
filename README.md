# Insurance-Data-Analysis-PowerBI-Dashboard

### Dashboard Link : https://app.powerbi.com/links/CBAkC02rGP?ctid=91577f61-0170-494b-a390-0f33a2bb8755&pbi_source=linkShare&bookmarkGuid=c4dd1f9f-d443-45e0-ab0c-ebef3b5b28a2

## Problem Statement

This dashboard helps **Prism Insurance Pvt. Ltd.** analyze their insurance portfolio and customer claim data. It provides insights into premium collections, coverage amounts, claim statuses, and customer sentiment — enabling the business to identify claim trends, understand policy performance across different categories, and improve customer experience.

Since 58.11% of policies are inactive, the business must focus on retention strategies. The dashboard also highlights claim rejection patterns and customer feedback sentiment to guide operational improvements.

---

## Project Highlights

- 3-page interactive Power BI report built on **10,000 records** from MSSQL Server
- Data cleaning and transformation performed entirely in **Power Query Editor**
- Includes **Drill Through** functionality for record-level investigation
- **Sentiment Analysis** page built using Word Cloud and customer feedback table
- **Row Level Security (RLS)** implemented and tested
- **Scheduled Refresh** configured and published to Power BI Service

---

## Data Source

- **MSSQL Server** (Microsoft SQL Server)
- Dataset: Insurance policy and claims data
- Records: **10,000 rows**, 15 columns
- Key columns: PolicyNumber, CustomerID, Gender, Age, PolicyType, PolicyStartDate, PolicyEndDate, CoverageAmount, PremiumAmount, ClaimNumber, ClaimDate, ClaimStatus, Active/Inactive, Age Group, Customer Feedback

---

## Steps Followed

### Data Import & Profiling

- **Step 1:** Loaded insurance dataset from MSSQL Server into Power BI Desktop.
- **Step 2:** Opened Power Query Editor. Under the View tab, enabled **Column Distribution**, **Column Quality**, and **Column Profile** options.
- **Step 3:** Set column profiling to **entire dataset** (default is top 1000 rows only).
- **Step 4:** All columns showed **100% Valid, 0% Error, 0% Empty** after cleaning.

### Data Cleaning in Power Query Editor

Applied Steps (visible in Query Settings):

- **Removed Duplicates** — handled duplicate records in the dataset
- **Replaced Value** — corrected specific inconsistent values
- **Added Conditional Column** — created **Age Group** column categorizing customers as Adult, Elder, Young Adult
- **Added Conditional Column1** — created **Active/Inactive** status column based on policy dates
- **Changed Type / Changed Type with Locale** — set correct data types for all columns including date columns with locale settings

### Report Building

- **Step 5:** Created 3 slicers — PolicyNumber, ClaimNumber, CustomerID — for flexible filtering.
- **Step 6:** Added 3 KPI card visuals for Premium Amount, Coverage Amount, and Claim Amount.
- **Step 7:** Added gender-wise customer count cards (Female: 5,000 | Male: 5,000).
- **Step 8:** Built bar chart for **Premium Amount by Policy Type**.
- **Step 9:** Built donut chart for **Count of Active vs Inactive Policies**.
- **Step 10:** Built line chart for **Claim Amount by Age Group**.
- **Step 11:** Added ribbon chart for **Number of Claims by Claim Status** (Rejected, Settled, Pending).
- **Step 12:** Built matrix visual showing **PolicyType × Claim Status** (Pending / Rejected / Settled) with totals.
- **Step 13:** Created **Page 2 — Drill Through** page showing detailed record-level table with all 15 columns, triggered from Page 1 visuals.
- **Step 14:** Created **Page 3 — Sentiment Analysis** page with:
  - **Word Cloud** visual built from customer feedback text
  - **Customer Feedback table** showing Customer Name and Feedback columns
- **Step 15:** Implemented **Row Level Security (RLS)** — created and tested roles in Power BI Desktop, then validated in Power BI Service.
- **Step 16:** Published report to Power BI Service and configured **Scheduled Refresh**.
- **Step 17:** Tested drill through filter functionality across pages.

---

## Report Snapshots

### Page 1 — Insurance Overview Dashboard (Power BI Desktop)

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/5dd0cbc9-fa50-48fb-8d62-fbc681b9866c" />

### Page 2 — Drill Through Detail View (Power BI Desktop)

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/dbc84720-53c1-406d-94d5-fbaea7ca41de" />

### Page 3 — Sentiment Analysis (Power BI Desktop)

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/044a4693-9a9e-4c1a-9f73-e6768adde694" />

### Power Query Editor — Data Cleaning Steps

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/816a1eb8-c1aa-4fd4-a4ed-06bba2327b9c" />

---

## KPIs

| KPI | Value |
|---|---|
| Total Premium Amount | 5.97M |
| Total Coverage Amount | 600.33M |
| Total Claim Amount | 16.90M |
| Active Policies | 4,190 (41.89%) |
| Inactive Policies | 5,810 (58.11%) |
| Female Customers | 5,000 |
| Male Customers | 5,000 |

---

## Visuals Used

| Visual | Purpose |
|---|---|
| Card | Premium Amount, Coverage Amount, Claim Amount, Gender count |
| Bar Chart | Premium Amount by Policy Type (Travel, Health, Auto, Life, Home) |
| Donut Chart | Active vs Inactive Policy distribution |
| Line Chart | Claim Amount by Age Group (Adult, Elder, Young Adult) |
| Ribbon Chart | Number of Claims by Claim Status over time |
| Matrix | PolicyType × Claim Status breakdown (Pending / Rejected / Settled) |
| Table (Drill Through) | Full record-level detail view |
| Word Cloud | Customer sentiment from feedback text |
| Table (Sentiment) | Customer Name and Feedback |
| Slicers | PolicyNumber, ClaimNumber, CustomerID |

---

## Claim Status Breakdown by Policy Type

| Policy Type | Pending | Rejected | Settled |
|---|---|---|---|
| Auto | 20,810,615.30 | 40,638,536.48 | 32,984,558.70 |
| Health | 27,682,791.20 | 52,401,928.42 | 40,017,100.67 |
| Home | 13,001,816.73 | 27,406,202.63 | 20,645,568.43 |
| Life | 17,259,587.93 | 33,722,751.49 | 23,121,204.63 |
| Travel | 57,060,548.78 | 107,395,611.51 | 86,182,353.59 |
| **Total** | **135,815,359.94** | **261,565,030.54** | **202,950,786.03** |

---

## Key Insights

- **58.11%** of policies are **inactive** — the business should focus on customer retention and policy renewal strategies.
- **Travel** policies contribute the highest claim amounts across all statuses.
- **Rejected claims (261.5M)** significantly exceed Settled (202.9M) and Pending (135.8M) — indicating a high rejection rate that may affect customer satisfaction.
- **Claim amounts decline** from Adult → Elder → Young Adult age group, suggesting younger customers file fewer/smaller claims.
- Customer sentiment analysis reveals mixed feedback — words like **"service"**, **"policy"**, **"process"**, and **"satisfied"** are prominent, but so are **"hassle"**, **"complex"**, and **"wait"** — areas needing improvement.
- Gender distribution is perfectly balanced — **50% Female, 50% Male**.

---

## Advanced Features Implemented

| Feature | Details |
|---|---|
| Drill Through Filter | Right-click any visual on Page 1 to drill through to full record detail on Page 2 |
| Row Level Security | Roles created and tested in Power BI Desktop, validated in Power BI Service |
| Scheduled Refresh | Configured in Power BI Service to keep data up to date |
| Sentiment Analysis | Word Cloud + feedback table on Page 3 using customer review text |
| Conditional Columns | Age Group and Active/Inactive columns added in Power Query |

---

## Tools & Technologies

- Microsoft SQL Server (MSSQL)
- Power BI Desktop & Power BI Service
- Power Query Editor (M Language)
- DAX (Data Analysis Expressions)
- Microsoft Excel (data staging)
