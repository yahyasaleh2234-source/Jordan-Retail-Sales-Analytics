# Project Report — Jordan Sales & Customer Data Analysis

## Executive summary
The supplied workbook audit reports 1,015 sales transactions, 1,000 customers, and a 33-column master table. Calculated sales value is **2,395,716.59**, derived from **893** rows with numeric Quantity and Unit Price. Another **122** rows remain in the dataset but have incomplete financial information. The monetary unit is unknown.

## Business context and scope
This is a descriptive Jordan-focused sales analytics case study. Its objective is to produce auditable analysis despite incomplete financial inputs and unreliable shipping sequences. It does not measure profitability, supplier quality, market opportunity, or causal effects.

## Preparation and methodology
- Keep original `Sales` and `Customers` sheets separate from working copies.
- Validate IDs and link sales to customers using Customer ID.
- Standardize raw sales-region labels with an auditable mapping to 12 regions.
- Preserve original category/provider fields and create cleaned grouping fields; blanks become explicit `Unknown` analytical groups.
- Only calculate `Sales_Value = Quantity × Unit_Price` if both inputs are numeric.
- Count *transaction rows* separately from nonblank and distinct Order IDs.
- Derive reporting month from Order Date; calculate shipping days as Ship Date minus Order Date, without masking negatives.

## Reported findings
| Dimension | Finding |
|---|---|
| Revenue eligibility | 893 / 1,015 = 87.98% |
| Calculated sales value | 2,395,716.59, currency unknown |
| Highest revenue region | Irbid: 239,863.46 (10.01%) |
| Lowest revenue region | Tafileh: 144,972.59 (6.05%) |
| Three leading regions | Irbid, Zarqa, Jerash: 695,816.10 (~29.05%) |
| Highest recorded month | May 2026: 263,015.96; 97 transaction rows |
| Largest category | Electronics: 430,050.14 |
| Blank-category analytical group | 174,441.19 (63 source records with blank categories) |
| Largest provider | Safeway: 431,724.86 |
| Blank-provider analytical group | 167,000.63 (65 source records with blank providers) |
| Highest customer-level revenue | 17,578.80; identifying information intentionally omitted |

Irbid is reported with 86 transaction rows, 75 revenue-eligible records, and eligible average value 3,198.18. Tafileh has 72 rows, 66 eligible, and average 2,196.55. These comparisons cannot establish regional sales efficiency.

## Data quality findings
- Missing Order IDs: 64; Quantity: 66; Unit Price: 62; both financial inputs: 6. Unique financially incomplete rows: 66 + 62 − 6 = 122.
- Three exact repeated original Sales row pairs: 47/1005, 205/1008, 902/1015. Retained pending owner confirmation.
- Shipping: 509 negative durations, 427 durations above provisional 30-day threshold, 79 between 0–30 days; all 1,015 accounted for.
- 63 category and 65 provider source labels are blank.
- Arabic/romanized sales-region mapping requires semantic approval.

## Recommendations
Reconcile missing financial inputs to authoritative records; confirm duplicate candidates; review mapping validity; investigate shipping-date meaning; and obtain pricing basis, costs, margins, efforts, and market data before strategic investment decisions.

## Conclusion
A solid descriptive analysis that makes data quality visible. Publication is not ready until the source data's redistribution rights and the privacy of customer records have been addressed.
