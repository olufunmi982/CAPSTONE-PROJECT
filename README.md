# CAPSTONE-PROJECT

# LITA-CAPSTONE-PROJECT (CUSTOMER DATA)

An overview of Incubator hub capstone customer dataset 

## ANALYSIS OF CAPSTONE PROJECT (CUSTOMER DATA)

### PROJECT OVERVIEW

This Analysis works on Capstone customer data set with the overview of the subscription trend of capstone customer data as it relates with some factors affecting the subscription types per Region.

### DATA SOURCES
- Microsoft Excel (Download Here)
- Capstone Customer data set

### Data Cleaning and Preparations

- Data cleaning was performed on Excel and this phase comprises of removal of duplicates, some columns were added and also there are some data types that neede to be changed , all these was done in this stage.

- Microsoft Excel was used for analysis with the aid of excel formulas and functions

- Visualization - the pivot table and pivot charts was used to summarise the reports of the analysis on Excel

### SQL (Structured Query Language)
This model was used to write to write queries for all necessary reports needed, clean data was imported from excel to SQL.

### Power BI, The data used on excel was also imported to Power BI

### DATA EXPLORATORY 
- Thorough data exploratory was done on Excel, SQL and Power BI.

- Some new columns were added in Excel, for example the Revenue column, some other were also added in SQL and Power BI

- Pivot tables and Pivot charts were used to summarise reports on excel

- Power BI visuals was used to present the reports on  power BI

### ANALYSIS ON EXCEL
- To Calculate the Subscription Duration
```
=F2-E2
```

- Total Revenue
```
=SUM(H2:H33788)
```
- Average Revenue
```
=AVERAGE(H2:H33788)
```
- Average Subscription Duration
```
=AVERAGE(I2:I33788)
```
- Total Revenue by Region
```
=SUM(C2:C33788,"Region",H2:H33788)
```

### Below are the visuals on Excel
![Excel customer data visual](https://github.com/user-attachments/assets/af6c03ad-8068-4266-a1eb-d39677553ece)

![Excel customer data visual 2](https://github.com/user-attachments/assets/8845a987-3e0d-457f-885c-6c703bdae2b4)

![Excel customer data visual 3](https://github.com/user-attachments/assets/324b2c65-0e28-4088-b5c7-530d8dc7eff1)

![Excel customer data visual 4](https://github.com/user-attachments/assets/5d992ac6-7465-4aab-9709-bca6da00da19)

![Excel customer data visual 5](https://github.com/user-attachments/assets/c1cfb013-63d0-4b8f-a3a1-66321e76977c)

![Excel customer data visual 6](https://github.com/user-attachments/assets/f8770029-b2ec-4fcf-a748-1e4fa0534f0b)

![Excel customer data visual 7](https://github.com/user-attachments/assets/1963f7c4-ff99-4764-b602-ed7185937076)

### Analysis on SQL
- Retrieve the total number of customers from each region
```
SELECT Region, COUNT(CustomerID) AS Total_No_of_Customers
FROM [dbo].[Customer Data]
GROUP BY Region
```
- Popular subscription type by the number of customers
```
SELECT SubscriptionType,COUNT(CustomerID)AS NO_Of_Customers
FROM [dbo].[Customer Data]
GROUP BY SubscriptionType
```
- Customers who canceled their subscription within 6 months
```
SELECT CustomerName,Canceled,SubscriptionStart
FROM [dbo].[Customer Data]
WHERE Canceled =0 AND MONTH(SubscriptionStart) BETWEEN 1 AND 6
```
- Average subscription duration for all customers
```
SELECT Count(CustomerID) As
All_Customers,AVG(DATEDIFF(DAY,SubscriptionStart,SubscriptionEnd)) AS
Average_Subscription_Duration
FROM [dbo].[Customer Data]
WHERE SubscriptionEnd IS NOT NULL
```
- Customers with subscriptions longer than 12 months
```
SELECT CustomerName,SubscriptionType,SubscriptionStart,SubscriptionEnd
FROM [dbo].[Customer Data]
WHERE DATEDIFF(MONTH,SubscriptionStart,SubscriptionEnd) >=12
```
- Total revenue by subscription type
```
SELECT SubscriptionType,SUM(Revenue) AS Total_Revenue
FROM[dbo].[Customer Data]
GROUP BY SubscriptionType
```
- Top 3 regions by subscription cancellations
```
SELECT TOP 3 Region,Canceled
FROM [dbo].[Customer Data]
```
- Total number of active and canceled subscriptions
```
SELECT
SUM( CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,
SUM (CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CanceledSubscriptions
FROM [dbo].[Customer Data]
GROUP BY CustomerID_
```

### POWER BI VISUALS

![Screenshot 2024-11-17 183433](https://github.com/user-attachments/assets/c3e102d2-dd9b-4e62-9134-9224ee3b9e1a)

