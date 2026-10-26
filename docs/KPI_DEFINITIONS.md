# KPI Definitions

All monetary-looking results are **currency-unconfirmed**, not guaranteed actual recognized revenue.

| KPI | Calculation / denominator | Reported result | Caution |
|---|---|---:|---|
| Transaction rows | Count sales records | 1,015 | Rows are not distinct orders |
| Nonblank Order ID rows | Count rows with known Order ID | 951 | Repeated IDs allowed |
| Distinct known Order IDs | Count unique nonblank IDs | 933 | Regional distinct counts are nonadditive |
| Missing Order IDs | Count blank IDs | 64 | No imputation |
| Financial completeness | Both inputs numeric / all rows | 893 / 1,015 = 87.98% | Completeness limited to two inputs |
| Financially incomplete | Missing or nonnumeric Quantity or Unit Price | 122 | Unknown values ≠ zero |
| Calculated revenue | Sum eligible Quantity × Unit Price | 2,395,716.59 | Currency and price basis unknown |
| Eligible average value | Calculated total / numeric Sales_Value count | 2,682.77 | Only 893 eligible rows |
| Regions represented | Distinct standardized region names | 12 | Mapping semantics unverified |
| Regional share | Region eligible sales / total eligible sales | Irbid: 10.01% | Not regional profitability |
| Monthly revenue | Sum eligible sales by Order_Month | May 2026: 263,015.96 | Boundary months partial |
| Category revenue | Sum by Category_Clean | Electronics: 430,050.14 | Unknown group included |
| Provider revenue | Sum by Provider_Clean | Safeway: 431,724.86 | Not supplier quality |
| Highest customer group | Sum by stable Customer ID | 17,578.80 | Do not expose identifying ID |
| Customer key match rate | Matched nonblank sales IDs / nonblank sales IDs | 100% reported | Assumes current key mapping |
| Negative shipping sequence | Count Ship_Date < Order_Date | 509 | Invalid for delivery KPI |
| Shipping over 30 days | Count positive durations >30 | 427 | Provisional screen |
| Shipping 0–30 days | Count 0 ≤ duration ≤30 | 79 | Not validated SLA performance |

**Key distinctions:** transaction rows ≠ nonblank Order ID rows ≠ distinct known Order IDs; Customer City ≠ Sales Region; an eligible average is not computed over all 1,015 rows. Four Order IDs reportedly span more than one region, meaning region-level distinct totals sum to 937 even though overall distinct IDs total 933.
