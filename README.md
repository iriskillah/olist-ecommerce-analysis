# Olist E-Commerce Analysis

Analysis of marketplace sales, delivery performance, and customer satisfaction using the Olist dataset. This report focuses on delivery performance.

**Project status:** Delivery analysis is complete and validated in Excel and Power BI. The next phase will explore how delivery delays relate to customer review scores.

## Power BI Delivery Analysis

[Download the Power BI report](./Olist%20E-Commerce%20Analysis.pbix)

- **Delivery Overview:** Of 96,470 eligible delivered orders, 6,534 (6.77%) arrived late. March 2018 had the highest late rate among months with at least 100 eligible orders, at 18.96%.
- **Delivery Exploration:** Late orders rose from 926 in February to 1,328 in March 2018. Minas Gerais and São Paulo accounted for 196 of the 402 net additional late orders.
- **Minas Gerais Deep Dive:** Orders with the same 21- or 22-day delivery estimate were late more often in March than in February. The 90th-percentile time from carrier handoff to delivery rose by about 7 days for the 21-day group and 10 days for the 22-day group. This points to post-handoff transit as a stage to investigate further.

## Excel Validation

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

## Next Analysis: Delivery Delays and Customer Reviews

**Question:** Were late orders more likely to receive a 1- or 2-star review?

1. Import `olist_order_reviews_dataset.csv` and check for missing or repeated `order_id` values. If an order has multiple review records, document how I choose one valid score before joining reviews to orders.
2. Compare on-time and late orders using the same delivery eligibility rules as the current report. For each group, show eligible orders, orders with a valid review, and review coverage.
3. Calculate the share of reviewed orders rated 1 or 2 stars in each group. Use review coverage to put the comparison in context.

## Data source

The Excel workbook uses the orders table. The Power BI report also uses the customers table to group orders by customer state. Both come from the [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce). The source dataset is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
