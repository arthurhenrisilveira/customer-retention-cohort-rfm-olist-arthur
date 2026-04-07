# Customer Retention & RFM Segmentation (Olist) — Python + Power BI

## Goal
Measure customer retention over time using cohort analysis and identify actionable CRM segments using RFM (Recency, Frequency, Monetary).

## Dataset
Brazilian E-Commerce Public Dataset by Olist (Kaggle).

## What you'll find in this repo
- `notebooks/`: Google Colab notebooks (data prep, cohort retention, RFM segmentation)
- `exports/`: curated tables exported from Python for Power BI
- `powerbi/`: Power BI dashboard (.pbix)
- `assets/`: dashboard screenshots
- `reports/`: 1-page case summary

## Deliverables
- Cohort retention heatmap (M0–M12)
- RFM segmentation (Champions, Loyal, At Risk, Hibernating, etc.)
- Lifecycle playbook: recommended actions & triggers by segment

## How to reproduce
1. Download the Olist dataset from Kaggle
2. Run notebooks in order (01 → 02 → 03)
3. Refresh the Power BI dashboard using files in `exports/`

## Tools
Python (pandas), Google Colab, Power BI
