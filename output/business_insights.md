# Business Insights from Executive Dashboard

## Calculated Fields Created in Tableau

| Calculated Field | Formula | Purpose |
|---|---|---|
| Profit Margin | `SUM([Profit]) / SUM([Sales])` | Measures profitability as a percentage |
| Cost | `[Sales] - [Profit]` | Derives cost per order for cost analysis |
| Average Order Value | `SUM([Sales]) / COUNTD([Order Id])` | Revenue per unique order |
| Return Rate | `SUM([Return Flag]) / COUNT([Order Id])` | Percentage of orders returned |
| Shipping Delay Bucket | `IF [Delivery Days] <= 2 THEN "Fast (1-2 days)" ELSEIF [Delivery Days] <= 4 THEN "Normal (3-4 days)" ELSEIF [Delivery Days] <= 6 THEN "Slow (5-6 days)" ELSE "Very Slow (7+ days)" END` | Groups delivery times for pattern analysis |
| Discount Bucket | `IF [Discount] <= 0.05 THEN "0-5%" ELSEIF [Discount] <= 0.15 THEN "5-15%" ELSEIF [Discount] <= 0.25 THEN "15-25%" ELSE "25%+" END` | Groups discount levels for impact analysis |

---

## Insight 1: Sales Trend — Seasonal Peaks in Jul-Aug and Oct-Nov

**Observation:** Monthly sales consistently peak in July-August and October-November across both 2024 and 2025, while April and June are consistent dip months.

**Evidence:** July 2025 recorded ₹1.07 Cr in sales (189 orders) vs April 2025 at ₹72 lakh (163 orders) — a 48% difference.

**Interpretation:** The Oct-Nov peak likely coincides with the festive season (Diwali, Navratri). The July-August spike may be driven by back-to-school and mid-year corporate procurement cycles.

**Action:** Pre-stock inventory and increase marketing budget 2-3 weeks before July and October. Introduce targeted promotions in April and June to smooth the revenue dip.

---

## Insight 2: Regional Performance — South Leads, East Lags in Efficiency

**Observation:** South region leads with ₹6.47 Cr in sales and ₹1.0 Cr profit. East generates the least sales (₹4.89 Cr) despite having a comparable number of orders.

**Evidence:** South has 1,210 orders with ₹53,548 average order value. East has 897 orders with ₹54,471 AOV but a higher return rate (4.9% vs 4.3% in West).

**Interpretation:** South benefits from higher order volume. East's lower total sales come from fewer orders, not lower order values — suggesting a demand generation problem rather than a pricing problem.

**Action:** Increase marketing investment in the East region to drive order volume. Investigate why East has the highest return rate — could be logistics or local service quality.

---

## Insight 3: Category Profitability — Technology Drives 84% of Profit

**Observation:** Technology accounts for ₹2.8 Cr of ₹3.33 Cr total profit (84%), despite being one of three categories.

**Evidence:** Technology margin is 18.2%, Furniture is 6.9%, Office Supplies is 14.9%. Within Technology, Copiers (₹73L profit), Accessories (₹72L), and Phones (₹71L) are the top contributors.

**Interpretation:** The business is heavily dependent on Technology for profitability. Furniture contributes significant revenue (₹5.16 Cr) but its low margin and high return rate make it a profit drag.

**Action:** Protect Technology margins by avoiding deep discounts on Copiers and Accessories. For Furniture, either improve margins through better sourcing or reduce the return rate to make the category sustainable.

---

## Insight 4: Customer Segment — Balanced but Home Office Slightly Leads

**Observation:** All three segments contribute nearly equally — Home Office (₹7.45 Cr), Consumer (₹7.19 Cr), Corporate (₹7.06 Cr).

**Evidence:** Profit margins are also similar across segments (15.0-15.5%), and no single segment has a disproportionate return rate.

**Interpretation:** This balance is a strength — the business is not over-reliant on any single segment. However, it also means there's no clear "best customer" to prioritize.

**Action:** Maintain balanced approach. Consider segment-specific campaigns — e.g., bulk order incentives for Corporate, loyalty programs for Consumer, productivity bundles for Home Office.

---

## Insight 5: Discount Impact — Margins Collapse Above 25%

**Observation:** Profit margin drops sharply as discounts increase: 19.8% at 0-5% discount, 15.0% at 5-15%, 11.2% at 15-25%, and just 6.5% at 25%+.

**Evidence:** 592 orders (14% of total) received discounts above 25%, averaging ₹2,729 profit per order vs ₹12,536 for low-discount orders — a 78% profit reduction.

**Interpretation:** Heavy discounting is not generating proportionally more volume. The business may be leaving significant profit on the table by over-discounting.

**Action:** Cap standard discounts at 20%. Use 25%+ only for end-of-season clearance. Train sales teams to lead with value rather than discount.

---

## Insight 6: Shipping Performance — Standard Class Dominates but Is Slowest

**Observation:** Standard Class accounts for 58% of all orders (2,435) with an average delivery of 4.7 days. Same Day is used for only 6% of orders.

**Evidence:** Same Day averages 0.4 days delivery, First Class 1.8 days, Second Class 2.7 days, Standard 4.7 days.

**Interpretation:** Customers may default to Standard Class because faster options aren't prominently offered or are priced too high. In a market where Amazon and Flipkart set 1-2 day delivery expectations, 4.7 days feels slow.

**Action:** Make First Class the default recommendation for orders above a certain value. Offer free shipping upgrades for first-time buyers to drive adoption.

---

## Insight 7: Return Pattern — Furniture Returns Are 2.5x Technology

**Observation:** Furniture has a 7.7% return rate vs 3.0% for Technology and 3.7% for Office Supplies.

**Evidence:** Of all Furniture orders, roughly 1 in 13 gets returned. Tables and Chairs are the likely drivers given their dominance in the Furniture category.

**Interpretation:** Furniture returns could stem from size/fit issues (customers can't judge dimensions online), quality mismatches, or delivery damage for large items. Each reason requires a different fix.

**Action:** Add detailed size guides and room mockup tools for Furniture. Audit packaging and delivery handling for Tables and Chairs. Consider offering Furniture-specific hassle-free returns to improve overall CX even if the return rate doesn't drop immediately.

---

## Insight 8: Business Risk — Profit Concentration and Discount Dependency

**Observation:** 84% of profit comes from one category (Technology), and 14% of orders are being sold at margins below 7%.

**Evidence:** If Technology margins drop by even 3 percentage points (due to competition or cost increases), total profit would fall by ₹46 lakh — a 14% hit to the bottom line.

**Interpretation:** The business has a concentration risk in Technology and a discipline risk in discounting. Both are manageable but need proactive attention.

**Action:** Diversify profit sources by improving Furniture margins (reduce returns, better sourcing). Implement a discount governance framework where any discount above 20% requires manager approval.
