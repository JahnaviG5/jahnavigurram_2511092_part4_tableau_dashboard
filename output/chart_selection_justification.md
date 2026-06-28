# Chart Selection Justification

## Chart 1: Sales Trend Over Time — Line Chart

**Question answered:** How are sales performing month over month? Are there seasonal patterns?

**Why line chart:** A line chart is the standard choice for time-series data because it shows continuity and directionality — you can immediately see whether sales are trending up, down, or cyclically. A bar chart would work for individual months but loses the visual flow of trends.

**Fields used:** Order Date (Month) on Columns, SUM(Sales) on Rows, color by Year to compare 2024 vs 2025.

**Design principle:** Dual-year comparison using color differentiation — allows leadership to see year-over-year patterns at a glance.

**Mistake avoided:** Did not use a stacked area chart, which would obscure the individual year trends and make comparisons harder.

---

## Chart 2: Regional Performance — Filled Map + Bar Chart

**Question answered:** Which regions and states drive the most sales and profit?

**Why map + bar chart:** A filled map leverages geographic intuition — leadership can immediately spot which parts of the country are strong or weak. A supporting bar chart adds precise numbers since maps alone make it hard to compare exact values.

**Fields used:** State on Detail, SUM(Sales) on Color (map). Region on Rows, SUM(Sales) and SUM(Profit) on Columns (bar chart).

**Design principle:** Sequential color gradient (light to dark blue) for the map — darker = higher sales. Consistent color coding between map and bar chart.

**Mistake avoided:** Did not use a pie chart for regional comparison — pie charts make it nearly impossible to compare similar-sized slices accurately.

---

## Chart 3: Category & Sub-Category Profitability — Horizontal Bar Chart

**Question answered:** Which categories and sub-categories generate the most profit? Where are the weak spots?

**Why horizontal bar chart:** Horizontal bars work best when category labels are long (like sub-category names). Sorting by profit makes it instantly clear which sub-categories lead and which lag.

**Fields used:** Sub-Category on Rows (sorted by profit), SUM(Profit) on Columns, Color by Category.

**Design principle:** Sorted descending by profit so the strongest performers are at the top. Color distinguishes the parent category without needing a separate legend lookup.

**Mistake avoided:** Did not use a treemap here — while treemaps show proportional size well, they make it hard to compare values precisely for categories of similar size.

---

## Chart 4: Customer Segment Comparison — Grouped Bar Chart

**Question answered:** How do sales, profit, and return rates compare across customer segments?

**Why grouped bar chart:** Grouped bars allow side-by-side comparison of multiple metrics across categories. This is cleaner than three separate charts and makes cross-segment comparison immediate.

**Fields used:** Customer Segment on Columns, SUM(Sales) and SUM(Profit) on Rows, Return Rate as a label.

**Design principle:** Consistent color — blue for sales, green for profit — across the entire dashboard. Segments ordered by sales descending.

**Mistake avoided:** Did not stack the bars — stacking would obscure the individual segment values and make profit look like it's "part of" sales rather than a separate metric.

---

## Chart 5: Discount vs Profit — Scatter Plot

**Question answered:** What is the relationship between discount levels and profitability?

**Why scatter plot:** Scatter plots are the correct choice for showing relationships between two continuous variables. Each dot represents an order, and the downward pattern makes the discount-profit tradeoff visually obvious.

**Fields used:** Discount on Columns, Profit on Rows, Color by Category, Size by Sales.

**Design principle:** Added a trend line to make the negative correlation clear even for non-technical viewers. Used transparency (low opacity) to handle overlapping points.

**Mistake avoided:** Did not use a bar chart of average profit by discount bucket — while useful as a summary, it hides the underlying variation and could mask outliers.

---

## Chart 6: Shipping Performance — Bar Chart with Delay Buckets

**Question answered:** Which shipping modes cause the longest delays? What is the delay distribution?

**Why bar chart:** Bar charts are ideal for comparing counts or averages across discrete categories (ship modes). Using the Shipping Delay Bucket calculated field adds actionable granularity.

**Fields used:** Ship Mode on Rows, CNT(Order Id) on Columns, Color by Shipping Delay Bucket.

**Design principle:** Used a diverging color scheme — green for fast delivery, red for slow — so the risk areas stand out immediately without reading labels.

**Mistake avoided:** Did not show average delivery days as a single number per ship mode — the distribution (how many orders fall in each delay bucket) is more actionable than the average alone.

---

## Chart 7: Return Analysis — Highlight Table

**Question answered:** Which categories and regions have the highest return rates?

**Why highlight table:** A highlight table (heat map) shows two dimensions simultaneously with color intensity indicating magnitude. This lets leadership spot problem intersections (e.g., Furniture + East) without scanning rows of numbers.

**Fields used:** Category on Rows, Region on Columns, Return Rate on Color and Label.

**Design principle:** Red-green diverging color — green for low return rates, red for high — makes problem areas jump out. Numbers are displayed inside cells for precision.

**Mistake avoided:** Did not use a line chart or bar chart — returns are better analyzed as rates across categories rather than as a time series, since the underlying pattern is structural, not temporal.

---

## KPI Cards (3 Summary Metrics)

**Question answered:** What are the headline numbers leadership needs to see first?

**Why KPI cards:** Executive dashboards should lead with the most important metrics in large, easy-to-read format. KPI cards serve as the dashboard's "headline" before the viewer dives into charts.

**Metrics shown:** Total Sales (₹21.7 Cr), Total Profit (₹3.33 Cr), Overall Profit Margin (15.3%).

**Design principle:** Large font, minimal decoration, positioned at the top of the dashboard. No chart chrome — just the number and the label.

**Mistake avoided:** Did not overload the KPI section with more than 3-4 cards — too many headline numbers create decision fatigue and dilute focus.
