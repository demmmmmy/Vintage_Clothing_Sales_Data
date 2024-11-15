# Vintage_Clothing_Sales_Data

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results and Findings](#results-and-findings)
- [Recommendations](#recommendations)

## Project Overview
This data analysis project aims to enhance sales strategies and performance and to improve inventory management, customer engagement and marketing efforts.

## Data Sources
- Vintage Clothing sales data: The primary dataset used for analysis is the "Vintage_Clothing_Sales_Data.csv" file, containing detailed information about sales made by the company.
- Customer id data: This dataset "customerid.csv" file, contains detailed information about each customers.
- Location data: This dataset "location.csv" file, contains detailed information about sales location.
- Payment data: this dataset "payment.csv" file, contains detailed information about the payments type.

## Tools
- Excel - Data Cleaning [download here](https://www.microsoft.com/en-us/microsoft-365/excel)
- SQL - Data Analysis [download here](https://dev.mysql.com/downloads/installer/)
- PowerBI

## Data Cleaning
In the data preparation phase, i performed the following tasks:
1. Data loading and inspection
2. Handling and editing missing values
3. Data cleaning and formating

## Exploratory Data Analysis
This involves exploring the vintage dataset to answer quesitons such as:
1. What is the total revenue generated from sales.
2. which the month in Vintage Couture generated the highest revenue. 
3. Which age group contributes the highest revenue.
4. what is the top 5 states by revenue.

## Data Analysis
``` SQL
SELECT Customer_Id, Gender,
CASE 
WHEN AGE BETWEEN 18 AND 30 THEN 'YOUNG_ADULT'
WHEN AGE BETWEEN 31 AND 40 THEN 'ADULT'
WHEN AGE BETWEEN 41 AND 49 THEN 'MIDDLE_AGED_ADULT'
ELSE 'SENIOR'
END AS AGE_GROUP
FROM customerid;

select
sum(case when age between 18 and 30 then amount else 0 end) as young_adult,
sum(case when age between 31 and 40 then amount else 0 end) as adult,
sum(case when age between 41 and 49 then amount else 0 end) as middle_aged_adult,
sum(case when age between 50 and 78 then amount else 0 end) as senior
FROM customerid CI
JOIN vintage_clothing_sales_data VC
ON CI.Customer_Id = VC.Customer_Id;
```
## Results and Findings
The analysis results are summarized as follows:
1. The customers aged 18 - 48 contribute to high revenue of the company.
2. The Gender with more revenue is Women generating almost x2 of the revenue of the Men.
3. The South-West region shows a relatively low revenue in all regions of the company.
4. Suits from the product category is the best-performing category in terms of sales and revenue.

## Recommendations
Based on the analyis i recommend the following actions:
- Ads Appealing to specific age clothing designs:
      customers aged 18 - 48 contribute to high revenue of the company, with customers aged 50 down to 80 having relatively less contribution to the revenue, and age 1- 17 having little to no contribution to the revenue.
Making clothes more suited for those ages with less and little to no contributions with ads to back them up, will help increase company's revenue.
- Gender:
      the Women generated the larger revenue with almost x2 of the revenue generated by the Men. If the company runs ads and promo with men clothing, more revenue should be generated from the men.
- Ads and promo in locations with relatively low locations and region:
      ads and promo can be run in all regions but most specifically in the South-West region, because it showed a relatively low revenue different from the other regions
- More product category:
      additional product category like Designer wears, Underwear can help improve business performances.

