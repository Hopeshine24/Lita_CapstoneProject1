# Lita_CapstoneProject1
### TOPIC: SALES PERFORMANCE ANALYSIS FOR A RETAIL STORE                                      

### Overview
This project collects and analyze the sales performance of a retail store, uncover key insights such as top-selling products, regional performance and monthly sales trends using the following steps and components:

## Data Collected
The dataset includes the following key columns:
- OrderID: Unique identifier for each order
- Customer Id: ID of the customer who placed the order.
- Product: The product name.
- Region: The region where the sale occurred.
- OrderDate: The date when the order was placed.
- Quantity: Number of units sold.
- UnitPrice: Price per unit.
- Sales: Total sales value (Quantity * UnitPrice).
## Project Objective
This project was designed to address the following analysis goals:
i. Total Sales By Product
ii. Total sales by Region
iii.  Total sales month
iv. Average sales per product
## Key Metrics:
- Total Sales: Measure of overall sales value.
- Top-selling Products: Products that contribute the most to revenue.
- Regional Sales: A breakdown of sales by different regions or stores.
- Monthly Trends: Insights into how sales vary over time.

## Tools Used
1. Miicrosoft Excel:
- Data cleaning: This is the removal of all unwanted attachment from your data,ensure there are no missing or inaccurate values provide data quality and consistency
- Data Analysis: Utilizing Excel's pivot tables and charting features, visualizations to uncover trends and insights related to different aspects of the dataset, summarize and filter the data for easier   interpretation, culminates in a visual dashboard which provides an overview of the sales data and allows users to explore key metrics and trends.
- Data Visualization: This provide the necessary context for data to be interpreted and acted upon.
2. SQL: Structured Query Language for quering data
3. Power BI for data modelling
4. Github for Portfolio building
## Visual Analysis
Pivot Table
i. Total Sales by Product:

ii. Total Sales By Region:

iii. Total Sales By Month:

### To calculate the metrics based on this data, we can use the following Excel formula:

 The AVERAGEIF formula to calculate the average sales for each product.
   
   =AVERAGEIF(C:C, "ProductName", H:H)

Bar Chart Showing Sales trend
Structured Query Language:
We will write queries to extract key insights based on the following:
1. The total Sales each each product category
```
   SELECT Product, SUM(Sales) AS Total_Sales
FROM [dbo].[Salesperformance]
GROUP BY Product;
```
2. Find the number of sales transactions in each region
```
SELECT Region, COUNT(OrderID) AS NumberOfTransactions
FROM [dbo].[Salesperformance]
group by Region
```
3. Find the highest-selling product by total sales value
```
SELECT Product, SUM(Sales) AS TotalSales
FROM [dbo].[Salesperformance]
GROUP BY Product
ORDER BY TotalSales DESC
```
4. Calculate total revenue per product
```
SELECT Product, SUM(Sales) AS TotalRevenue
FROM Lita_LatestProject
GROUP BY Product;
```
6. Calculate Monthly sales for the current year
```
SELECT strftime('%Y-%m', OrderDate) AS Month, SUM(Sales) AS MonthlyTotal
FROM Lita_LatestProject
WHERE strftime('%Y', OrderDate) = '2023'
GROUP BY Month
ORDER BY Month;
```
8. Find the 5 top customers by purchase amount
```
SELECT "Customer_id", SUM(Sales) AS TotalPurchaseAmount
FROM Lita_LatestProject
GROUP BY "Customer_id"
ORDER BY TotalPurchaseAmount DESC

Power BI

