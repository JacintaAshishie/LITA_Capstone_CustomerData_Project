# Customer-Segmentation-Analysis

## Project Overview
This project aims to analyze customer data to understand subscription behavior, track trends, and identify key segments.



## Data Sources
The primary Data used here is CustomerData.xslx. This data provide the LITA at IncubatorHub and was made available for download from CANVAS. Other Similar datasets can be freely downloaded from an open source oinline such as Kaggle or FRED or any other repository sites.


## Tools Used

- Excel for data cleaning and preparation

- SQL Server for data analysis
```
SELECT 
    CustomerID, 
    SubscriptionStart, Canceled
FROM 
    [dbo].[CAPSTONE CLEANED  CUSTOMERDATA ]
WHERE 
    DATEDIFF(month, SubscriptionStart, Canceled) <= 6
```
 
- Power BI for data visualization

## Data Dictionary
Outline the terminology and definitions of key column headers specific to the dataset. This section ensures clarity for anyone reviewing the project.

- CustomerID: Unique identifier for each customer.
- CustomerName: Name of the customer.
- Region: Geographic area where the customer is located.
- SubscriptionType: Type of subscription chosen by the customer.
- SubscriptionStart: Date when the subscription began.
- SubscriptionEnd: Date when the subscription ended.
- Canceled: Indicates if the subscription was canceled (True/False).
- Revenue: Income generated from the customer's subscription.

## Data Cleaning and Preparation
In the initial phase of the data cleaning and preparations, we preform the following actions;
- Data inspection and loading
- Handling missing variables
- Data cleaning and formatting

## Exploratory Data Analysis (EDA)

 ### Customer Subscriptions
This involved analysing the data to answer the following questions;

- The total number of customers from each region.
- The most popular subscription type by the number of customers.
- Customers who canceled their subscription within 6 months.
- The average subscription duration for all customers.
- Customers with subscriptions longer than 12 months.
- The total revenue by subscription type.
- Top 3 regions by subscription cancellations.
- The total number of active and canceled subscriptions.



## Data Analysis
### SQL queries for data analysis:

 1.  Retrieve the total number of customers from each region.
 
```Select  region, count(distinct Customerid) as total_customers 
from [dbo].[CustomerData]
Group by region;
```

2. Find the most popular subscription type by the number of customers. 

```Select top 1 subscriptiontype, count(distinct customerid) as total_customers
From  [dbo].[CustomerData]
Group by subscriptiontype 
Order by total_customers desc;
```

 3. Find customers who canceled their subscription within 6 months. 
```Select customerid
From [dbo].[CustomerData]
Where datediff (month, subscriptionstart, subscriptionend) <= 6;
```

4.   Calculate the average subscription duration for all customers. 
```Select avg(datediff(day, subscriptionstart, subscriptionend)) as avg_subscription_duration
From [dbo].[CustomerData]
```

5.  Find customers with subscriptions longer than 12 months. 

```SELECT CustomerID
FROM [dbo].[CustomerData]
WHERE DATEDIFF(month, SubscriptionStart, SubscriptionEnd) > 12;
```

6. Calculate total revenue by subscription type.

```Select Subscriptiontype,
Sum(revenue) as Total_revenue 
From [dbo].[CustomerData]
Group by subscriptiontype;
```

7.  Find the top 3 regions by subscription cancellations. 

```Select top 3 region,
Count(*) as subscriptionend_count
From [dbo].[CustomerData]
Where subscriptionend is null
Group by region
Order by subscriptionend_count desc;
```
 
## Data Visualization
### Power BI dashboard:    
- Customer-Segmentation DashBoard ((https://github.com/JacintaAshishie/LITA_Capstone_CustomerData_Project/blob/main/CUSTOMER-%20SEGMENTATION%20DASHBOARD.png))
-  Most Popular SubscriptionTypes ((https://github.com/JacintaAshishie/LITA_Capstone_CustomerData_Project/blob/main/M%2COST%20POPULAR%20SUBSCRIPTION%20TYPE.png))
- Sum of Revenue By SubscriptionType ((https://github.com/JacintaAshishie/LITA_Capstone_CustomerData_Project/blob/main/SUM%20OF%20REVENUE%20BY%20SUBSCRIPTION%20TYPE.png))
- Average Revenue By SubscriptionType ((https://github.com/JacintaAshishie/LITA_Capstone_CustomerData_Project/blob/main/AVERAGE%20REVENUE%20BY%20SUBSCRIPTION%20TYPE.png))
- Count of Customers By Canceled ((https://github.com/JacintaAshishie/LITA_Capstone_CustomerData_Project/blob/main/COUNT%20OF%20CUSTOMER%20ID%20BY%20CANCELED.png))



