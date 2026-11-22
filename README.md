# Financial Sales Profitability Dashboard (Power BI)

An end-to-end Power BI project that finds which customer segments and discount levels erode profit. Built on 700 sales transactions with Power Query, a star schema, and DAX.

**Business question:** Which customer segments and discount levels erode profit, and what should the company do about it?

## Dashboard preview

![Executive Summary](images/page1_executive_summary.png)
![Segment and Product](images/page2_segment_product.png)
![Discount and Loss](images/page3_discount_loss.png)

## Key findings

- **Enterprise is the only segment losing money.** 19.6M in sales but -0.6M in profit (margin -3.1%). All 58 loss-making transactions (-777K) belong to Enterprise, and only at Medium and High discounts.
- **Higher discounts shrink margin.** Margin falls from 21.9% (no discount) to 17.9% (Low), 14.4% (Medium), and 9.1% (High). The decline holds inside every segment.
- **Government drives profit** (about two-thirds of total profit at a 21.7% margin). **Small Business** is large (36% of sales) but thin at a 9.8% margin.
- **Sep-Dec 2014 sales grew 36.9%** versus the same months of 2013.

Recommendations are framed as hypotheses to validate, for example reviewing approval rules for Medium and High discounts on Enterprise deals.

## What I did

1. **Data preparation (Power Query):** fixed column names and types, created a surrogate key, and split a flat table into a fact table and dimension tables.
2. **Data modeling:** star schema with `Fact_Sales` and five dimensions (Date, Product, Segment, Country, Discount Band), all one-to-many with single-direction filters.
3. **DAX:** Total Sales, Total Profit, Profit Margin %, Discount Rate %, Loss Transactions, Loss Amount, and time-intelligence measures (Sales LY, Sales YoY %).
4. **Design:** wireframed the three pages in Figma, then built them in Power BI with conditional formatting that reserves red for losses.

![Data model](images/model_view.png)

## Dashboard pages

| Page | What it answers |
|---|---|
| Executive Summary | How is the business performing overall? |
| Segment & Product | Which segments are big but thin, and which lose money? |
| Discount & Loss | How do discounts affect margin, and where do losses occur? |

## Tools

Power BI Desktop, Power Query, DAX, Figma

## Repository contents

```
├── financial_sales_dashboard.pbix   Power BI report
├── data/                            source data
├── images/                          dashboard and model screenshots
└── README.md
```

To explore the report, open the `.pbix` file in Power BI Desktop (Windows).

## Dataset

Sales dataset from Kaggle: [dataset name and link]. 700 transactions, Sep 2013 to Dec 2014, across 5 segments, 5 countries, and 6 products.

## Limitations

- The dataset appears synthetic, so findings describe patterns in this data, not real-world truths.
- The data is a flat table with no customer or order ID, so customer-level analysis was not possible.
- 2013 covers only Sep-Dec, so year-over-year comparisons are valid only for those months.
- The data does not explain why discounts were given, so the discount-margin link is an association, not proof of cause.

## Author

**Anavadya Dyra Trinanda** · Junior Data Analyst
[LinkedIn](www.linkedin.com/in/anavadya-dyra-trinanda) · [Portfolio](https://porto-data-analyst-anavadya.notion.site/Portfolio-Data-Analyst-95fde24c37c483848d2a01398cd90e2e)
