# Power BI Sales Analytics with Executive Dashboards & Paginated Reporting

---

## Project Overview

This project demonstrates end-to-end business intelligence development using Microsoft Power BI, combining executive dashboards, advanced DAX calculations, and paginated reporting for detailed transactional analysis.

The solution showcases both interactive analytics and structured enterprise-style reporting suitable for business performance monitoring and decision support.

---

## Key Highlights

- Executive sales performance dashboard  
- Detailed sales analytics report  
- Paginated transaction reporting using Power BI Report Builder  
- Custom DAX measures supporting KPI analysis  
- Professional dashboard layout and user-focused design  

---

## Data Source

**Dataset:** Superstore Sales Dataset (sample BI dataset)

Includes:

- Customer information  
- Product categories and subcategories  
- Sales transactions  
- Profitability data  
- Shipping details  

---

## Tools & Technologies

- **Power BI Desktop** – Dashboard development  
- **Power BI Service** – Report publishing and sharing  
- **Power BI Report Builder** – Paginated reporting  
- **DAX (Data Analysis Expressions)** – Measures and KPIs  
- **GitHub** – Documentation and version control  

---

## Project Components

### Executive Dashboard

Provides high-level business performance insights including:

- Revenue trends  
- Profitability indicators  
- Regional sales distribution  
- Category-level performance analysis  
- KPI tracking  

Designed primarily for executive decision-making.

---

### Detailed Sales Analysis Dashboard

Focuses on deeper analytical insights:

- Year-over-year performance metrics  
- Top customers and products analysis  
- Interactive filtering by year, region, category, and segment  
- Transaction-level summaries  

---

### Paginated Reporting (Key Feature)

Developed using **Power BI Report Builder** to demonstrate enterprise reporting capabilities:

- Pixel-perfect formatted reports  
- Parameterized year filtering  
- Transaction-level tabular reporting  
- Print-ready professional layout  
- Export support (PDF, Excel, Print)

This component highlights advanced reporting skills beyond standard dashboard development.

---

## Key DAX Measures

Below are selected DAX measures developed for KPI tracking, executive dashboards, and paginated reporting.
Examples of measures implemented:

- Total Sales  
- Total Profit  
- Profit Margin %  
- Sales Year-to-Date (YTD)  
- Year-over-Year Growth  
- Average Order Value  

### Measures and their formula's

Total Sales

Total Sales = SUM('Orders'[Sales])

Total Profit

Total Profit = SUM('Orders'[Profit])

Total Quantity

Total Quantity = SUM('Orders'[Quantity])
Profitability Measures

Profit Margin %

Profit Margin % =
DIVIDE([Total Profit], [Total Sales], 0)

Average Order Value

Average Order Value =
DIVIDE([Total Sales], DISTINCTCOUNT('Orders'[Order ID]), 0)
Time Intelligence Measures

Sales Year-to-Date (YTD)

Sales YTD =
TOTALYTD([Total Sales], 'Dim_Date'[Date])

Profit Year-to-Date

Profit YTD =
TOTALYTD([Total Profit], 'Dim_Date'[Date])

Sales Last Year

Sales LY =
CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Dim_Date'[Date]))

Year-over-Year Growth %

Sales YoY % =
DIVIDE([Total Sales] - [Sales LY], [Sales LY], 0)
Reporting Support Measures (Paginated Reports)

Selected Year Parameter Display

Selected Year Label =
IF(
    ISBLANK(SELECTEDVALUE('Dim_Date'[Year])),
    "All Years",
    SELECTEDVALUE('Dim_Date'[Year])
)

Used for dynamic titles and paginated report headers.

These measures support executive dashboards, detailed analytical reports, and paginated transaction reporting.

---

## Repository Structure
Power-BI-Sales-Analytics-Project/
│
├── data/ # Dataset files
├── dashboards/ # Power BI dashboard (.pbix) files
├── paginated-reports/ # Paginated report (.rdl) files
├── dax/ # DAX measures documentation
├── images/ # Dashboard screenshots
└── README.md # Project documentation


---

## Skills Demonstrated

- Business Intelligence development  
- Data modeling and transformation  
- Advanced DAX calculations  
- Dashboard design and storytelling  
- Paginated enterprise reporting  
- Technical documentation and version control  

---

## Future Improvements

- Automated dataset refresh pipeline  
- Expanded KPI framework  

---

## Author

**Obianuju Lynda Nzurumike**  
Data Analyst |BI Developer| Data Engineer| Business Intelligence analyst
---