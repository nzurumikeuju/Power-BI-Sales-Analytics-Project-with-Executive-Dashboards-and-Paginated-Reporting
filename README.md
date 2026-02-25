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

