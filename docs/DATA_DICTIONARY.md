# Data Dictionary

## Master sales — `tbl_MasterSales`

Reported range: `Master_Sales!A1:AG1016`; 1,015 data rows, 33 fields. The first ten fields originate from Sales. The remaining fields are derived, lookup, or audit fields.

| Field | Origin | Definition |
|---|---|---|
| `Order_ID` | Original | Order key; blanks retained |
| `Order_Date` | Original | Date the order was recorded |
| `Ship_Date` | Original | Reported ship date; chronology not assumed valid |
| `Order_Status` | Original | Recorded status |
| `Sales Region` | Original | Raw sales region, separate from customer city |
| `Customer ID` | Original | Customer relationship key |
| `Category` | Original | Raw product category; blanks retained |
| `Provider_Name` | Original | Raw provider label; blanks retained |
| `Quantity` | Original | Numeric quantity or blank |
| `Unit_Price` | Original | Unit price or blank, currency unknown |
| `Order_ID_Status` | Derived | Present/missing flag |
| `Quantity_Status` | Derived | Presence/status of quantity |
| `Unit_Price_Status` | Derived | Presence/status of price |
| `Financial_Completeness_Status` | Derived | Complete if both quantity and unit price are numeric |
| `Customer_ID_Match` | Derived | Number of customer-master key matches |
| `Customer_Name_Lookup` | Lookup | Customer display label; sensitive |
| `Customer_City` | Lookup | Customer city; not sales region |
| `Sales_Region_Clean` | Mapping | Standardized region |
| `Sales_Value` | Derived | Quantity × unit price when both numeric; else blank |
| `Shipping_Days` | Derived | Ship date minus order date |
| `Shipping_Status` | Derived | Negative date-sequence flag or review status |
| `Shipping_Days_Valid` | Derived | 0–30-day provisional screen only, not valid delivery KPI |
| `Row_Record_ID` | Derived | Technical row key; not an Order ID |
| `Order_Month` | Derived | Month-start date from Order Date |
| `Sales_Region_Mapping_Status` | Derived | Mapped/unmapped status |
| `Revenue_Eligible_Flag` | Derived | 1 where Sales_Value numeric |
| `Financially_Incomplete_Flag` | Derived | 1 for incomplete financial inputs |
| `Shipping_Days_Over_30_Flag` | Derived | Provisional count flag |
| `Shipping_Days_0_30_Flag` | Derived | Provisional count flag |
| `Category_Clean` | Mapping | Cleaned grouping including Unknown |
| `Provider_Clean` | Mapping | Cleaned grouping including Unknown |
| `Order_ID_Region_Unique_Flag` | Derived | First known ID occurrence per region |
| `Unique_Order_ID_Overall_Flag` | Derived | First known ID occurrence overall |

## Supporting working sheets

- `SALES_WORKING` (`tbl_SalesWorking`, reported `A1:X1016`): original sales fields, status flags, customer lookups, region mapping, calculated value, shipping quality, and source row lineage.
- `CUSTOMERS_WORKING` (`tbl_CustomersWorking`, reported `A1:N1001`): 8 raw customer fields plus city/name clean fields and quality checks. Contains identifying data; **not for unrestricted public distribution**.
- `Region_Mapping` has source map `A1:B50` and 72-row audit table `D1:G73`.
- `Category_Mapping` (`tbl_CategoryMap`, 42 mapping rows); `Provider_Mapping` (`tbl_ProviderMap`, 41 mapping rows).
- `Customer_ID_Analysis` groups by stable customer ID; `Additional_Analysis` contains coverage and duplicate-evidence tables.

The dictionary derives from final-session documentation; confirm precise references against the publication copy once available.
