# Olist E-Commerce Analysis

Analysis of marketplace sales, delivery performance, and customer satisfaction using Power BI and the Olist dataset.

**Project status:** Spreadsheet validation for delivery performance is complete. The Power BI report is in development.

## Delivery findings

Of the **96,470 delivered orders with a recorded actual delivery date and an estimated delivery date**, **6,534 (6.77%)** arrived after their estimated date. The remaining **89,936 (93.23%)** arrived on or before it.

| Delivery timing | Orders | Share of eligible orders |
| --- | ---: | ---: |
| Before the estimated date | 88,644 | 91.89% |
| On the estimated date | 1,292 | 1.34% |
| After the estimated date | 6,534 | 6.77% |
| **Total eligible** | **96,470** | **100.00%** |

[Download the original analysis workbook](https://raw.githubusercontent.com/iriskillah/olist-ecommerce-analysis/main/analysis/Orders%20dataset%20with%20analysis.xlsx). Start with the **Findings** and **Analysis** tabs, then see **Assumptions** and **Data Quality Notes** for the decisions behind the numbers.

## How I measured delivery timeliness

1. Checked the grain of the orders table. It contains 99,441 rows with unique, populated order IDs.
2. Limited the comparison to orders marked delivered with both actual and estimated delivery dates. Eight of 96,478 delivered orders lacked an actual delivery date and were excluded from the rate.
3. Subtracted the estimated calendar date from the actual calendar date. Delivery on the estimated date counts as on time. Estimated timestamps were recorded at midnight, so I used calendar dates as a project assumption.
4. Investigated the largest variances and retained the flagged records. Across the eligible orders, 52 (0.05%) arrived more than 90 days before or after the estimate.

## Next step in Power BI

Rebuild the delivery calculation from the source CSV and reconcile the results to the workbook. Then explore sales trends and product categories, compare delivery performance by month and region, and investigate how delivery timing relates to customer review scores.

## Data source

The workbook uses the orders table from the [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce). The source dataset is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
