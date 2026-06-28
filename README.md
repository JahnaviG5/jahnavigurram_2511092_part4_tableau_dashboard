# Part 4: Tableau Executive Dashboard & Data Storytelling

**Jahnavi Gurram | bitsom_ba_2511092**

---

## Business Problem Summary

The retail leadership team needs an interactive executive dashboard to monitor sales performance, profitability, customer segments, category health, shipping efficiency, discount impact, and return patterns. The dashboard should help identify business opportunities and risks, not just display charts.

---

## Dataset Description

| Property | Value |
|---|---|
| File | dashboard_sales_data.xlsx |
| Records | 4,200 orders |
| Time period | January 2024 – December 2025 |
| Regions | North, South, East, West |
| Categories | Technology, Furniture, Office Supplies |
| Segments | Home Office, Consumer, Corporate |
| Key metrics | Sales, Profit, Discount, Return Flag, Delivery Days, Customer Rating |
| Missing values | campaign_channel (24), customer_rating (32) |

---

## Tableau Workbook Description

The packaged workbook (`executive_dashboard.twbx`) contains:
- 1 executive dashboard with 7 charts and 3 KPI cards
- 7 individual worksheet views (one per required analysis area)
- 6 calculated fields
- 4 interactive filters (Region, Category, Customer Segment, Date)
- Filter actions enabling cross-chart interaction

---

## Calculated Fields Created

| Field | Formula | Purpose |
|---|---|---|
| Profit Margin | `SUM([Profit]) / SUM([Sales])` | Profitability percentage |
| Cost | `[Sales] - [Profit]` | Cost per order |
| Average Order Value | `SUM([Sales]) / COUNTD([Order Id])` | Revenue per order |
| Return Rate | `SUM([Return Flag]) / COUNT([Order Id])` | Return percentage |
| Shipping Delay Bucket | IF/ELSEIF on Delivery Days → Fast/Normal/Slow/Very Slow | Delivery performance groups |
| Discount Bucket | IF/ELSEIF on Discount → 0-5%, 5-15%, 15-25%, 25%+ | Discount impact analysis |

---

## Dashboard Components

| View | Chart Type | Purpose |
|---|---|---|
| KPI Cards | Text/BAN | Total Sales, Total Profit, Profit Margin |
| Sales Trend | Line Chart | Monthly sales over time, year-over-year |
| Regional Performance | Map + Bar Chart | Sales and profit by region/state |
| Category Profitability | Horizontal Bar | Sub-category profit ranking |
| Customer Segment | Grouped Bar | Segment comparison |
| Discount vs Profit | Scatter Plot | Discount-profit relationship |
| Shipping Performance | Bar Chart | Delay distribution by ship mode |
| Return Analysis | Highlight Table | Return rates by category and region |

---

## Filters and Interactions

| Filter | Type | Applied To |
|---|---|---|
| Region | Dropdown | All views |
| Category | Dropdown | All views |
| Customer Segment | Dropdown | All views |
| Date Range | Slider | Sales trend and related views |
| Filter Action | Click-based | Clicking a region on the map filters all other charts |

---

## Key Business Insights

1. **Sales peak in Jul-Aug and Oct-Nov** — seasonal patterns are consistent and plannable
2. **South region leads** (₹6.47 Cr) while East has the highest return rate (4.9%)
3. **Technology drives 84% of all profit** — heavy concentration risk
4. **Furniture returns at 7.7%** — 2.5x the rate of Technology
5. **Discounts above 25% collapse margins** to 6.5% (vs 19.8% at low discount)
6. **Standard Class shipping** (58% of orders) averages 4.7 days — slowest option
7. **Customer segments are balanced** — no over-reliance on one group
8. **Organic channel drives 41% of sales** — most cost-efficient acquisition source

---

## Dashboard Story Summary

The business is healthy at the topline (₹21.7 Cr sales, 15.3% margin) but faces three key risks: profit concentration in Technology, unsustainable Furniture return rates, and margin erosion from over-discounting. Recommended actions include capping discounts at 20%, auditing Furniture returns, increasing April/June marketing, and promoting faster shipping options.

---

## Assumptions and Limitations

- Return reasons are not available — only a binary flag exists
- Campaign attribution is single-touch, not multi-touch
- 2-year window is too short for robust long-term trend analysis
- Customer lifetime value is not captured in the dataset
- Dashboard shows association, not causation — e.g., high discounts correlate with low profit, but the relationship may not be purely causal

---

## Screenshots

| File | Shows |
|---|---|
| screenshots/full_dashboard.png | Complete executive dashboard |
| screenshots/sales_trend_view.png | Monthly sales line chart |
| screenshots/regional_performance_view.png | Map or bar chart of regional sales |
| screenshots/category_profitability_view.png | Sub-category profit bars |
| screenshots/filter_interaction_view.png | Dashboard with a filter applied |
