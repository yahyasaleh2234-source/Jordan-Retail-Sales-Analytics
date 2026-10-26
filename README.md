# Jordan Sales & Customer Data Analysis | Excel Portfolio Project 2

**Excel data cleaning · Data-quality audit · PivotTables · Interactive dashboard · Descriptive sales analysis**

> **Publication note:** The underlying workbook has not been included in this public-ready package because its customer data may be personally identifying and redistribution rights are unconfirmed. The source workbook must be sanitized and validated before publication. Amounts are shown without a currency symbol because the currency has not been verified.

![Sales revenue by region](assets/regional_revenue.png)

## Project overview

This Excel portfolio case study analyzes sales transactions and their related customer records, with an emphasis on transparent handling of incomplete financial inputs, inconsistent categorical labels, and questionable shipping dates. The analysis preserves incomplete rows rather than imputing unknown values or deleting them.

## Business questions

- Which Jordanian sales regions contribute the most calculated revenue?
- How do region-level transaction volumes and eligible average transaction values compare?
- How does revenue vary by month, product category, provider, and customer?
- How much of the source data is financially complete, and what limits reliable reporting?

## Dataset and verified reported results

| Metric | Result |
|---|---:|
| Source sales rows | 1,015 |
| Customer records | 1,000 |
| Master sales fields | 33 (10 original + 23 added) |
| Revenue-eligible sales rows | 893 |
| Financially incomplete sales rows | 122 |
| Financial completeness | 87.98% |
| Calculated sales value (currency unconfirmed) | 2,395,716.59 |
| Standardized sales regions | 12 |
| Date range | 8 Sep 2025 – 7 Sep 2026 |

These results are based on workbook analysis and the supplied Excel audit/documentation. The final publication workbook and its formula behavior require review when a sanitized workbook is available.

## Featured findings

- **Irbid** leads the 12 regions with **239,863.46** (10.01% of calculated sales value); **Tafileh** is lowest with **144,972.59** (6.05%).
- **May 2026** has the highest recorded monthly sales value at **263,015.96**; the September boundary months are incomplete.
- **Electronics** has the highest cleaned category value (**430,050.14**). The unknown category group contributes **174,441.19**.
- **Safeway** leads the cleaned provider grouping at **431,724.86**; the unknown provider group contributes **167,000.63**.
- **509** shipping dates precede order dates. Delivery-speed performance cannot be inferred from this dataset without correcting the underlying date semantics.

![Financial data quality](assets/financial_data_quality.png)

## Methods and tools

Microsoft Excel; structured Tables; `IF`, `AND`, `ISNUMBER`, `SUM`, `COUNTIF`/`COUNTIFS`, `XLOOKUP`, `TRIM`, `UNIQUE`, and lookup/mapping workflows; PivotTables; standard charts; formula-driven Region/Month dashboard filters. The workflow was AI-assisted; no Power Query work was verified.

Revenue is calculated as `Quantity × Unit_Price` **only where both values are numeric**. All 1,015 transaction rows remain in the dataset. The 122 financially incomplete records have blank calculated revenue, not zero. Revenue averages use the 893 eligible rows rather than all 1,015 rows.

## Screenshots

- [Regional revenue chart](assets/regional_revenue.png)
- [Dataset overview](assets/data_quality_overview.png)
- [Financial data quality](assets/financial_data_quality.png)

Other dashboard screenshots were excluded because they showed customer names or identifiers. A privacy-safe dashboard image can be added after redaction.

## Limitations

- Missing financial inputs mean the calculated revenue total does not represent all transactions.
- Currency, tax treatment, and discount basis are unknown.
- 64 Order IDs are missing; 3 exact repeated source-row pairs were retained for review.
- 63 category values and 65 provider values are blank in the original sales source.
- Sales-region variant mappings require business-owner semantic review.
- Shipping duration contains 509 negative date sequences; a 30-day screen is provisional, not a delivery SLA.
- The source dataset contains names, identifiers, phone numbers, ages, and locations. Publication of the original workbook is **not approved** by this package.

## Repository guide

| File | Description |
|---|---|
| [Project report](docs/PROJECT_REPORT.md) | Business context and findings |
| [Data dictionary](docs/DATA_DICTIONARY.md) | Original and derived fields |
| [Cleaning log](docs/DATA_CLEANING_LOG.md) | Preparation and quality decisions |
| [KPI definitions](docs/KPI_DEFINITIONS.md) | Metric formulas, denominators, caveats |
| [Business insights](docs/BUSINESS_INSIGHTS.md) | Interpreted findings and recommendations |
| [Quality assurance report](docs/QUALITY_ASSURANCE_REPORT.md) | Tests, reconciliations, known limits |
| [Requirements compliance](docs/REQUIREMENTS_COMPLIANCE.md) | Assignment checklist status |
| [Publication checklist](docs/GITHUB_UPLOAD_CHECKLIST.md) | Required release checks |
| [Manifest](docs/PROJECT_MANIFEST.md) | Actual delivered file inventory |

## Reproducibility

A finished, public-safe Excel workbook is not included. The full workflow requires access to authorized source sheets, transformation formulas, mapping tables, and Excel workbook objects. The described Region/Month dropdown filters are not native slicers. Without the original workbook, this repository documents the method and results but does not yet contain an independently runnable spreadsheet artifact.

## Status

**Documentation package prepared; workbook publication blocked by privacy/rights review.** See [publication checklist](docs/GITHUB_UPLOAD_CHECKLIST.md).
