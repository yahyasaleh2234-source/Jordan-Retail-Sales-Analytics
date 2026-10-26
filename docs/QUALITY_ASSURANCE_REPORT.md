# Quality Assurance Report

This report summarizes audit tests **reported by the Excel add-in** and supporting workbook review; it is not a guarantee that every formula or interactive Excel object was independently exercised in a sanitized publication copy.

| Test | Reported actual | Assessment |
|---|---:|---|
| Source Sales rows | 1,015 | Reconciled |
| Source Customers rows | 1,000 | Reconciled |
| Master Sales fields | 33 | Reconciled against final field list |
| Financially eligible rows | 893 | Reconciled |
| Financially incomplete rows | 122 | Reconciled |
| Calculated sales value | 2,395,716.59 | Reconciled across regional, monthly, category, provider, customer totals |
| Region contribution totals | 100% | Reported pass |
| Sales region mapping | 1,015 mapped; 0 unmapped | Pass with semantic review |
| Shipping classifications | 509 + 427 + 79 = 1,015 | Reconciled |
| Exact repeated rows | 3 original source-row pairs | Retained for owner review |
| Dashboard Region/Month dropdown tests | Multiple combinations, All reset | Reported pass; retest in released file |
| Formula error scan | No common errors reported | Scoped; not an exhaustive independent audit |

## Workbook inventory
16 visible worksheets, 15 Excel Tables, 4 native PivotTables, and 6 charts reported: five on dashboard and one regional chart in Sales Analysis.

## Unresolved tests and qualifications
1. Direct chart source ranges and full defined-name/external-link inventory were not confirmed by the Excel add-in.
2. Original assignment PDF was not available during its last acceptance test.
3. Region mapping semantic correctness requires business-owner signoff.
4. Date sequences, currency, original category/provider blanks, and duplicate candidates remain unresolved.
5. Original source data contains personally identifying customer fields, and rights are unknown.
6. Historical checklist documentation recorded 29 master fields at an earlier point; final report supports **33 fields** (10 original + 23 derived).
7. A privacy-safe publication workbook has **not** been verified.

**Publication assessment:** documentation may be prepared, but publishing the raw Excel workbook is blocked pending privacy and distribution checks.
