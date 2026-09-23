# Retail-Sales-Profitability-Analytics-PowerBI
Interactive Power BI dashboard for analyzing retail sales, profitability, and target performance.
# 📊 Retail Sales & Profitability Analytics — Power BI

## 📌 Project Overview

This project is an interactive Power BI dashboard developed to analyze retail sales, profitability, and target performance.

The dashboard provides insights into sales trends, regional performance, product performance, customer segments, profitability, and target achievement.

## 🎯 Business Objectives

- Analyze overall sales performance
- Track sales and profit trends over time
- Identify top-performing products
- Compare sales performance across regions
- Analyze profitability and profit margins
- Compare actual sales against targets
- Identify regions performing above or below targets

- ## 🛠️ Tools & Technologies

- Power BI
- Power Query
- DAX
- Data Modeling
- Star Schema
- CSV
- Data Visualization

- ## 📂 Dataset

The project uses a retail sales dataset containing sales transactions, targets, products, customers, regions, and dates.

### Fact Tables

- **FactSales** — Sales transaction data
- **FactTarget** — Regional sales target data

### Dimension Tables

- **DimProduct** — Product information
- **DimCustomer** — Customer information
- **DimRegion** — Regional information
- **DimDate** — Date, month, quarter, and year information

## 🧹 Data Cleaning

Data preparation was performed using Power Query.

Key steps included:

- Checking and correcting data types
- Removing duplicate records
- Handling missing values
- Replacing missing discount values
- Calculating missing sales values
- Removing unnecessary spaces
- Creating a Date dimension
- Creating Month Number for correct month sorting
- Preparing tables for data modeling

  ## 🏗️ Data Model

The project follows a Star Schema.

### Main Relationships


DimDate ────────► FactSales
   │
   └────────────► FactTarget

DimRegion ──────► FactSales
   │
   └────────────► FactTarget

DimProduct ─────► FactSales

DimCustomer ────► FactSales

## 📐 Key DAX Measures

### Total Sales
``DAX
Total Sales = SUM(FactSales[Sales])

Total Profit
Total Profit = SUM(FactSales[Profit])
Total Cost
Total Cost = SUM(FactSales[Cost])
Total Quantity
Total Quantity = SUM(FactSales[Quantity])
Total Transactions
Total Transactions = COUNTROWS(FactSales)
Average Sales per Transaction
Average Sales per Transaction =
DIVIDE(
    [Total Sales],
    [Total Transactions]
)
Profit Margin %
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales]
)
Previous Year Sales
Previous Year Sales =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(DimDate[OrderDate])
)
YoY Sales Growth %
YoY Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales]
)
YTD Sales
YTD Sales =
TOTALYTD(
    [Total Sales],
    DimDate[OrderDate]
)
YTD Profit
YTD Profit =
TOTALYTD(
    [Total Profit],
    DimDate[OrderDate]
)
Total Target
Total Target = SUM(FactTarget[Target])
Target Variance
Target Variance =
[Total Sales] - [Total Target]
Target Achievement %
Target Achievement % =
DIVIDE(
    [Total Sales],
    [Total Target]
)
YTD Target
YTD Target =
TOTALYTD(
    [Total Target],
    DimDate[OrderDate]
)
YTD Target Achievement %
YTD Target Achievement % =
DIVIDE(
    [YTD Sales],
    [YTD Target]
)



# 📊 Dashboard Pages

## 1. Sales Overview

The Sales Overview page analyzes overall sales performance.

### Key Metrics

- Total Sales
- Total Quantity
- Total Transactions
- Average Sales per Transaction
- YoY Sales Growth %

### Visualizations

- Sales by Month
- Sales by Region
- Top 10 Products by Sales
- Sales by Product Category
- Average Order Value by Region

![Sales Overview](sales-overview.png)

---

## 2. Profitability Analysis

The Profitability Analysis page focuses on profit performance.

### Key Metrics

- Total Profit
- Profit Margin %

### Visualizations

- Profit by Month
- Profit by Region
- Profit by Product Category
- Top 10 Products by Profit
- Profit by Customer Segment
- Profit vs Sales by Region

![Profitability Analysis](profitability-analysis.png)

---

## 3. Target vs Actual Performance

This page compares actual sales performance with business targets.

### Key Metrics

- Total Target
- Total Sales
- Target Achievement %
- Target Variance

### Visualizations

- Actual Sales vs Target by Month
- Target Achievement % by Region
- Target Variance by Region
- Target Achievement % by Month
- Target by Region

![Target vs Actual](target-vs-actual.png)


# 🔄 Project Workflow


Raw Data
   ↓
Data Cleaning
   ↓
Power Query
   ↓
Data Modeling
   ↓
Star Schema
   ↓
DAX Measures
   ↓
Dashboard Development
   ↓
Business Analysis



# 💡 Key Analysis

The dashboard allows users to analyze:

- Sales trends
- Regional sales performance
- Product performance
- Profitability
- Profit margins
- Customer segment performance
- Target achievement
- Target variance
- Actual vs target performance

  # 📁 Project Files

| File | Description |
|---|---|
| Retail_Sales_Profitability_Analytics.pbix | Power BI dashboard |
| FactSales.csv | Sales transaction data |
| FactTarget.csv | Sales target data |
| DimProduct.csv | Product data |
| DimCustomer.csv | Customer data |
| DimRegion.csv | Region data |
| sales-overview.png | Sales dashboard |
| profitability-analysis.png | Profitability dashboard |
| target-vs-actual.png | Target dashboard |

# 👨‍💻 Author

## Shiva Pavan Kumar Gunisetti

Data Analyst | Data Scientist

**Skills:** Python, SQL, Power BI, Excel, Pandas, NumPy, Machine Learning, Data Visualization,Deep Learning

---

⭐ If you find this project useful, feel free to explore the repository.
