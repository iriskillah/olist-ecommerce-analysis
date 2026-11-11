# Olist E-Commerce Analysis

A Power BI project exploring marketplace sales, delivery performance,
and customer satisfaction.

## Project status
Spreadsheet delivery analysis validated. Power BI implementation is next.

## Business questions
- How do monthly orders and product sales change over time?
- Which product categories contribute the most sales?
- Which customer regions experience the most late deliveries?
- How does delivery performance relate to customer review scores?

## Tools
- Excel / Google Sheets
- Power BI Desktop
- Power Query
- DAX

## Dataset
Brazilian E-Commerce Public Dataset by Olist.

Source: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Spreadsheet delivery validation

[Download the validation workbook](analysis/olist-delivery-validation.xlsx). It contains the analysis results, metric assumptions, and data quality notes as a snapshot. Download `olist_orders_dataset.csv` from the dataset link above to reproduce the analysis.

Among 96,470 delivered orders with both dates available, **6,534 (6.77%) arrived after the estimated calendar date**. The other 89,936 (93.23%) arrived on or before it. Eight orders marked delivered were excluded from the rate because their actual delivery date was missing.
