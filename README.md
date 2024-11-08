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

## Data Cleaning and Preparation
 Data cleaning steps:
   - Handling missing values
   - Data normalization
   - Data transformation
    
  ## Data preparation steps:
   - Data merging
   - Data aggregation

## Exploratory Data Analysis (EDA)

 - Univariate analysis:
  - Distribution of subscription types
  - Distribution of customer demographics
- Multivariate analysis:
    - Correlation between subscription types and customer demographics
    - Relationship between subscription duration and cancellation rate



## Data Analysis
- SQL queries for data analysis:
    - Total customers by region
    - Most popular subscription type
    - Customers who canceled within 6 months
    - Average subscription duration
    - Total revenue by subscription type
 
## Data Visualization
- Power BI dashboard:
    - Customer segmentation
    - Cancellation trends
    - Subscription trends
    - Revenue analysis
    



