# coffee-shop-sales-dashboard-excel
Excel dashboard analysing 149K coffee shop transactions: KPIs, peak hours, product mix and store comparison.

# Coffee Shop Sales Dashboard | Excel

An interactive, single-page Excel dashboard that analyses six months of transaction data for **Maven Roasters**, a fictitious coffee shop chain with three New York City locations. The report tracks sales performance, peak trading hours, product mix and store comparison, and summarises the findings in a short insights panel.

---

## Objective

Give store and regional managers a clear view of how the business is performing, answering five questions:

1. How is the business performing overall?
2. How have sales trended over time?
3. Which days of the week are busiest?
4. What times of day are busiest, and does the pattern hold across stores?
5. Which products and categories drive the most sales and revenue?

## Dataset

| Item | Detail |
|---|---|
| Source | [Maven Analytics: Coffee Shop Sales](https://mavenanalytics.io/data-playground/coffee-shop-sales) (public domain) |
| Period | 1 January 2023 to 30 June 2023 |
| Volume | 149,116 transactions |
| Locations | Astoria, Hell's Kitchen, Lower Manhattan |
| Fields | Transaction ID, date, time, quantity, store, product ID, unit price, product category, product type, product detail |

## Tools and Techniques

- **Microsoft Excel:** Tables, PivotTables, PivotCharts, slicers, timeline, conditional formatting (data bars), linked pictures
- **Power Query:** data quality checks
- **Data Model and DAX:** measures built with `SUMX`
- **Formulas:** `TEXT`, `WEEKDAY`, `IF` for calculated columns

## KPIs

| KPI | Definition | Value |
|---|---|---|
| Total Revenue | Sum of quantity x unit price | ₹698.8K |
| Total Transactions | Count of transactions | 149.1K |
| Total Quantity | Sum of items sold | 214.5K |
| Average Transaction Value | Total Revenue / Total Transactions | ₹4.69 |
| Average Items per Transaction | Total Quantity / Total Transactions | 1.44 |

## Methodology

1. **Data preparation:** loaded the raw data into an Excel Table and ran data quality checks in Power Query. No duplicate records or blank values were found.
2. **Feature engineering:** created calculated columns for hour, month, month name, weekday number, weekday name and a Weekday/Weekend flag.
3. **Measures:** built revenue, average transaction value and average items per transaction as measures, with revenue calculated using `SUMX` over quantity and unit price.
4. **Analysis:** built PivotTables for the monthly trend, hourly and weekday patterns, category mix, store revenue and top products.
5. **Dashboard:** assembled the charts, KPI cards and Top 15 products table (with data bars) on one page, connected to slicers for weekday, store and product category and a date timeline, so every element filters together.
6. **Navigation:** the workbook has four sheets (Transactions, Analysis, Dashboard, Contacts), linked by navigation buttons.

## Dashboard Components

- Five KPI cards
- Monthly revenue trend with trendline
- Transactions by hour of day
- Transactions by weekday
- Transactions by product category
- Revenue by store
- Top 15 products by transactions, with revenue and data bars
- Insights panel

## Key Insights

- **Revenue roughly doubled** from ₹81.7K in January to ₹166.5K in June. February dipped slightly, and growth was strongest in March and May.
- **Peak trading runs from 8 to 10 am**, with transactions highest at 10 am.
- **Coffee and Tea lead sales**, with 58.4K and 45.4K transactions out of 149.1K.
- **Revenue is evenly split across the three stores:** Hell's Kitchen ₹236.5K, Astoria ₹232.2K and Lower Manhattan ₹230.1K.
- **Among the top 15 products by transactions**, Brewed Chai Tea and Gourmet Brewed Coffee sell most often, and Barista Espresso earns the highest revenue (₹91.4K).

## Limitations

- Six months of data is not enough to assess seasonality.
- The dataset has no customer or cost information, so repeat-customer, retention and profitability analysis are not possible.
- The model uses a single flat transactions table with no relationships.

## Future Enhancements

- Exceptions report listing the lowest-selling products
- Notes sheet with KPI definitions and update instructions
- Automated refresh using a Power Query folder load
- Split data model with separate Transactions, Products and Stores tables
