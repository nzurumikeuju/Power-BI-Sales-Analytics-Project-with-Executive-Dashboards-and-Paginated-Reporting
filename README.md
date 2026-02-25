# Power BI Sales Analytics with Executive Dashboards & Paginated Reporting

## Project Overview
This project demonstrates end-to-end business intelligence development using Power BI, including executive dashboards, advanced DAX measures, and paginated reporting for detailed transaction-level analysis.

## Key Highlights
- Executive sales performance dashboard
- Detailed sales analytics report
- Paginated transaction reporting (Power BI Report Builder)
- Custom DAX measures for KPIs
- Professional dashboard design and UX

## Tools Used
- Power BI Desktop
- Power BI Report Builder
- DAX
- Excel / Superstore Dataset

## Repository Structure
- `/data` → Dataset
- `/powerbi` → Power BI reports
- `/paginated-reports` → Paginated reports (.rdl)
- `/dax` → Measures documentation
- `/screenshots` → Dashboard previews

## Author
** Obianuju Lynda Nzurumike**  
Data Analyst | BI Developer | Data Analytics Engineer

DAX Measures & Calculations

This project makes extensive use of DAX (Data Analysis Expressions) to support executive-level analytics, year-over-year comparisons, and paginated reporting.

🔹 Core Measures
Total Sales =
SUM ( Fact_Sales[Sales] )

Total Profit =
SUM ( Fact_Sales[Profit] )

Total Quantity =
SUM ( Fact_Sales[Quantity] )

🔹 Time Intelligence Measures
Sales YTD =
TOTALYTD (
    [Total Sales],
    Dim_Date[Date]
)

Sales LY =
CALCULATE (
    [Total Sales],
    SAMEPERIODLASTYEAR ( Dim_Date[Date] )
)

Sales YoY % =
DIVIDE (
    [Total Sales] - [Sales LY],
    [Sales LY]
)

🔹 Profitability Metrics
Profit Margin % =
DIVIDE (
    [Total Profit],
    [Total Sales]
)
Average Order Value =
DIVIDE (
    [Total Sales],
    DISTINCTCOUNT ( Fact_Sales[Order ID] )
)

🔹 Paginated Reporting Support

To support Power BI Paginated Reports, measures were optimized for:

Row-level detail rendering

Parameter-driven filtering (Year selection)

Print-friendly layouts

Example Year filter logic used in paginated datasets:

IF (
    SELECTEDVALUE ( Dim_Date[Year] ) = "ALL",
    TRUE(),
    Dim_Date[Year] = SELECTEDVALUE ( Dim_Date[Year] )
)
🔹 Design Considerations

Measures were created at semantic model level to ensure reuse across:

Executive dashboards

Detailed analysis pages

Paginated reports

Time intelligence relies on a dedicated Date Dimension

Paginated Reporting (Power BI Report Builder)

This project includes a fully developed Paginated Report created using Power BI Report Builder to demonstrate advanced reporting capabilities such as parameterization, DAX-based dataset queries, and print-optimized layout design.

Report Overview

The paginated report delivers a structured, print-ready Sales Transaction Report designed for operational reporting, auditing, and detailed transaction analysis. It complements the interactive dashboards by providing highly formatted tabular output suitable for export to PDF, Excel, or print distribution.

Dataset and Query Design

Dataset sourced from a published Power BI semantic model.

Custom DAX query dataset used instead of a direct table connection.

Parameter-driven filtering implemented using a report parameter (@Year).

Conditional logic supports both:

Single-year filtering

Full dataset view ("All Years")

Example filtering logic:

IF(
    SelectedYear = "ALL",
    TRUE(),
    Dim_Date[Year] = VALUE(SelectedYear)
)

This ensures compatibility between numeric date fields and text-based parameter values.

Parameter Implementation

Year parameter configured with:

Available values list (2015–2019 plus "All Years")

Default value handling

Parameter displayed dynamically in the report header.

Used within the DAX dataset query to control filtering.

Report Layout and Formatting

Corporate-style header including:

Report title

Prepared-by information

Generated timestamp

Selected year indicator

Tabular layout optimized for readability:

Alternating row shading using RowNumber(Nothing)

Consistent header styling

Currency formatting for sales and profit

Designed specifically for export and print fidelity.

Key Report Fields

Order Date

Customer Name

Product Name

Ship Mode

Total Sales

Total Profit

Technical Skills Demonstrated

Power BI Report Builder paginated report development

DAX query authoring for report datasets

Parameterized report filtering logic

Print-ready report design and formatting

Integration between Power BI semantic model and paginated reports

Deliverables

.rdl paginated report file

Power BI dataset connection

Exportable report output (PDF/Excel compatible)