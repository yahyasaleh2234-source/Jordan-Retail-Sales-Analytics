# Data Cleaning and Quality Decision Log

## Preservation
1,015 Sales records and 1,000 Customers records were retained. No values were imputed. Missing identifiers and financial fields were kept unknown.

## Financial inputs
| Issue | Rows |
|---|---:|
| Missing Order ID | 64 |
| Missing Quantity | 66 |
| Missing Unit Price | 62 |
| Missing both Quantity and Unit Price | 6 |
| Unique financially incomplete | 122 |
| Eligible for calculated sales value | 893 |

`Sales_Value` is blank unless both financial inputs are numeric, never inferred as zero.

## Repeated source rows
| Original Sales worksheet rows | Decision |
|---|---|
| 47 and 1005 | Exact candidate; retain pending owner review |
| 205 and 1008 | Exact candidate; retain pending owner review |
| 902 and 1015 | Exact candidate; retain pending owner review |

951 rows have nonblank Order IDs, versus 933 distinct known IDs. This distinction is **not** an exact duplicate count.

## Customer keys and text
1,000 customer records; no missing or repeated master IDs reported. All nonblank sales customer IDs reportedly matched. Separate cleaned customer names/cities were retained; latest reported clean versions apply `TRIM`, not assumed name corrections. City and Sales Region remain distinct.

## Mappings
12 canonical regions with 1,015 mapped sales records, but the observed 72-row reference and the original mapping variant counts need reconciliation and semantic approval. Blank source categories (63) and providers (65) appear as `Unknown` groups in analysis. Ambiguous variants are not merged by assumption.

## Dates
All 1,015 Order Dates and Ship Dates were numeric. The ship minus order calculation yields 509 negative, 427 above the provisional 30-day screen, and 79 in provisional 0–30 days. No source dates were modified; no absolute-value workaround was used.

## Data handling
The customer sheets contain names, IDs, phone numbers, ages, and locations. Keep these out of public workbooks without permission and a validated sanitization process.
