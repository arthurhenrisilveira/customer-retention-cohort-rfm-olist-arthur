# Customer Retention & RFM Segmentation (Olist) — Python + Power BI

## Business Question
How can cohort retention analysis and RFM segmentation help identify CRM opportunities to improve repeat purchase behavior, prioritize reactivation, and support lifecycle decision-making?

## Project Overview
This project explores customer retention and segmentation using the **Brazilian E-Commerce Public Dataset by Olist**.

The analysis combines two complementary perspectives:

- **Cohort retention analysis** to understand repeat purchase behavior over time
- **RFM segmentation** to classify customers into actionable CRM groups based on recency, frequency, and monetary value

The final output includes:
- a data preparation pipeline built in **Python (Google Colab)**
- curated exports for analysis and BI consumption
- a **Power BI dashboard** with:
  - cohort retention heatmap
  - RFM segment distribution
  - revenue by segment
  - CRM action recommendations by segment

---

## Dataset
**Source:** Brazilian E-Commerce Public Dataset by Olist (Kaggle)

Main files used:
- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_customers_dataset.csv`
- `olist_products_dataset.csv`

---

## Project Goals
The main goals of this case study were:

1. Build a clean **order-level fact table** from raw transactional files
2. Measure **month-by-month repeat purchase retention** using cohort analysis
3. Segment customers using **RFM (Recency, Frequency, Monetary)**
4. Translate analytical outputs into **practical CRM actions**

---

## What I Built

### 1) Data Preparation
I transformed multiple raw transactional tables into a clean **order-level fact table**, including:
- unique customer identifier
- purchase timestamp
- order-level revenue
- item count

This created the analytical foundation for retention and customer-level segmentation.

### 2) Cohort Retention Analysis
I grouped customers by **first purchase month** and measured the share of each cohort that returned to purchase in subsequent months.

This produced a **cohort retention heatmap** showing month-by-month repeat purchase activity.

### 3) RFM Segmentation
I built a customer-level RFM model using:
- **Recency** = days since last purchase
- **Frequency** = number of unique orders
- **Monetary** = total revenue generated

Customers were then classified into CRM-friendly segments such as:
- Champions
- Loyal Customers
- Potential Loyalists
- New Customers
- At Risk
- Hibernating
- Needs Attention

### 4) Power BI Dashboard
I designed a two-part dashboard:
- **Cohort retention page**
- **RFM segmentation page**, including:
  - total customers
  - total revenue
  - top revenue segment
  - customers by segment
  - revenue by segment
  - segment summary
  - recommended CRM actions

---

## Key Insights

### 1. At Risk emerged as the most important CRM opportunity
The **At Risk** segment combined:
- the **largest customer base**
- the **highest revenue contribution**

This suggests that winback initiatives targeting recently lapsed high-value customers may unlock meaningful business value.

### 2. Hibernating customers still represent significant historical revenue
Although **Hibernating** customers showed very poor recency, they still accounted for a large share of cumulative revenue.

This indicates reactivation potential, though likely requiring a more selective and cost-conscious approach than At Risk campaigns.

### 3. Champions have the highest average customer value
The **Champions** segment had the strongest monetary profile, reinforcing the importance of:
- retention
- loyalty strategies
- referral or exclusivity programs

### 4. New Customers highlight second-purchase opportunity
The **New Customers** segment showed the freshest recency profile but low scale and low total revenue.

This reinforces the importance of onboarding and **second-purchase activation** to improve early lifecycle conversion.

### 5. Cohort retention showed low month-by-month repeat purchase activity
The cohort heatmap revealed that repeat purchase activity declines quickly across acquisition cohorts.

This suggests that the business opportunity may lie in:
- improving early repeat purchase conversion
- reducing drop-off after first purchase
- creating stronger lifecycle interventions in the first months

---

## CRM Recommendations by Segment

| Segment | Goal | Recommended Action | Timing |
|---|---|---|---|
| Champions | Retain and grow top customers | Loyalty, referral, exclusives | Ongoing |
| Loyal Customers | Increase frequency and basket size | Cross-sell, bundles, engagement | 15–30 days |
| Potential Loyalists | Convert into loyal repeat buyers | Second-order incentive | 7–21 days |
| New Customers | Drive second purchase | Welcome/onboarding journey | 7–14 days |
| At Risk | Win back valuable lapsed customers | Reactivation campaign | 30–60 days |
| Hibernating | Selectively reactivate inactive customers | Strong offer and reminder | 60+ days |
| Needs Attention | Prevent further drop-off | Light engagement/reminder | 15–30 days |

---

## Repository Structure

    customer-retention-cohort-rfm-olist/
    │
    ├── notebooks/
    │   ├── 01_data_prep.ipynb
    │   ├── 02_cohort_retention.ipynb
    │   └── 03_rfm_segmentation.ipynb
    │
    ├── exports/
    │   ├── orders_fact.csv
    │   ├── orders_fact_light.csv
    │   ├── cohort_retention_long.csv
    │   ├── cohort_retention_long_ptbr.csv
    │   ├── rfm_customers.csv
    │   ├── rfm_customers_ptbr.csv
    │   ├── rfm_segment_summary.csv
    │   └── rfm_segment_summary_ptbr.csv
    │
    ├── powerbi/
    │   └── OlistDash.pbix
    │
    ├── assets/
    │   ├── cohort_heatmap.png
    │   └── rfm_dashboard.png
    │
    └── README.md

---

## Tools Used
- **Python**
- **pandas**
- **Google Colab**
- **Power BI**

---

## Method Summary

### Notebook 01 — Data Prep
Built a clean order-level fact table by:
- loading raw Olist transactional data
- calculating order-level revenue
- mapping customer IDs to unique customers
- exporting curated analytical tables

### Notebook 02 — Cohort Retention
Measured month-by-month repeat purchase activity by:
- identifying each customer’s first purchase month
- assigning customers to cohorts
- calculating active customers and retention rate per month index

### Notebook 03 — RFM Segmentation
Segmented customers by:
- recency
- frequency
- monetary value

Then assigned CRM-friendly segment labels and created summary tables for dashboarding.

---

## Dashboard Overview

### Cohort Retention Page
- customer retention heatmap by cohort month
- month-by-month repeat purchase view

### RFM Segmentation Page
- total customers
- total revenue
- top revenue segment
- customers by segment
- revenue by segment
- segment summary
- recommended CRM actions

---

## How to Reproduce
1. Download the Olist dataset from Kaggle
2. Place the CSV files in the expected data directory
3. Run the notebooks in order:
   - `01_data_prep`
   - `02_cohort_retention`
   - `03_rfm_segmentation`
4. Use the exported files in `/exports/`
5. Open the Power BI file and refresh the data connections if needed

---

## Limitations
This project is intended as a portfolio case study and has some limitations:

- Cohort retention was measured as **month-by-month repeat purchase activity**, not cumulative retention
- RFM thresholds were based on quantile scoring, which is practical but not industry-specific
- No campaign execution or uplift testing was performed
- Segment definitions were simplified for analytical clarity and dashboard communication

---

## Next Steps
Possible future extensions include:

- **Second Purchase Rate within 90 Days**
- **Cumulative Repeat Purchase by Cohort**
- category-level behavioral analysis
- campaign prioritization framework
- estimated reactivation opportunity sizing by segment

---

## Author
**Arthur Henrique Silveira Santos**  
Analytics / CRM / Growth / Customer Insights

GitHub: [arthurhenrisilveira](https://github.com/arthurhenrisilveira)
