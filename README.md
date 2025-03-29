# Global SuperStore Report

![Introduction](Introduction.png)

## Introduction
This is a Power BI project on the sales analysis of an imaginary store called "Global SuperStore". The objective of this project is to analyze the dataset and provide answers to business questions.

**_Disclaimer_**: _All datasets and reports do not represent any company, institution, or country. It is just a dummy datatset used to demonstrate the capabilities of Power BI._

## Problem Statement

1.  What are the three countries that generated the highest total profit for Global Superstore in 2014? (b) For each of these three countries, find the three products with the highest total profit. 
2. Identify the 3 subcategories with the highest average shipping cost in the United States.
3. Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African countries? (b) What factors might be responsible for Nigeria’s poor performance?
4. Identify the product subcategory that is the least profitable in Southeast Asia.  Note: For this question, assume that Southeast Asia comprises Cambodia, Indonesia, Malaysia, Myanmar (Burma), the Philippines, Singapore, Thailand, and Vietnam. (b) Is there a specific country i n Southeast Asia where Global Superstore should stop offering the subcategory identified in 4a?  
5. Which city is the least profitable (in terms of average profit) in the United States? (b) Why is this city’s average profit so low?  
6. Which product subcategory has the highest average profit in Australia?  
7. Who are the most valuable customers and what do they purchase?

 ## Skills/Concepts Demonstrated 
 
The following Power BI features where incorporated:
- Power Query (Data cleaning and transformation),
- Data Modeling,
- DAX,
- Data Presentation (Visualizations),
- Filters and Interactivity

## Data Sourcing

The dataset used for this analysis was sourced from the Global Superstore dataset, it contains transactional data related to customer orders, shipping, profitability and returns.
The data was stored in an excel file with multiple sheets, including:
- Orders Table
- Returns Table
- People Table

## Data Transformation

Before analysis, the dataset underwent data cleaning and transformation in power query. 
Key steps include: 
- Removing duplicates,
- Handling missing values,
- Standardizing data types,
- Extracting order year column and filtered data.

## Data Modeling

![Data modeling](data-modeling.PNG)

The Global SuperStore data model was structured using a star schema approach, with the order table as the central fact table, returns and people tables as the two dimensions table. Both were joined to the fact table with a one-to-many relationship.

## DAX Measures

The following DAX measures were used to calculate key metrics within the dataset:
-	Avg Discount Nigeria = CALCULATE(AVERAGE(Orders[Discount]),Orders[Country]="Nigeria")
-	Avg Profit Australia = CALCULATE(AVERAGE(Orders[Profit]), Orders[Country]="Australia")
-	Avg Profit Per Order = DIVIDE(SUM(Orders[Profit]), COUNT(Orders[Order ID]))
-	Avg Shipping Cost = AVERAGE(Orders[Shipping Cost])
-	Avg Shipping Cost Nigeria = CALCULATE(AVERAGE(Orders[Shipping Cost]),Orders[Country]="Nigeria")
-	Total Profit = CALCULATE(SUM(Orders[Profit]))
-	Total Profit 2014 = CALCULATE(SUM(Orders[Profit]),YEAR(Orders[Order Date])=2014)
-	Total Profit Nigeria 2014 = CALCULATE(SUM(Orders[Profit]),Orders[Country]= "Nigeria",YEAR(Orders[Order Date])=2014)
-	Total Profit SE Asia = CALCULATE(SUM(Orders[Profit]),Orders[Country] IN {"Cambodia","Indonesia","Malaysia","Myanmar","Philippines","Singapore","Thailand","Vietnam"})

##### This project documentation contains screenshots of data visualization as a means to interpret and easily read results gotten from my analysis.

## Data Analysis and visualization

![Dashboard](Dashboard.PNG)

- #### What are the three countries that generated the highest total profit for Global Superstore in 2014?

  In 2014,the three countries that generated the highest total profit for global superstore are:
  1. United States with $93,507.5
  2. India with $48,807.6
  3. China with $46,793.9
 
- #### (b) For each of these three countries, find the three products with the highest total profit.
  
  ##### 3 Products with the highest profit in United States
  1. Canon ImageCLASS 2200 Advanced Copier with $15,679.95
  2. Hewlett Packard Laserjet 3310 Copier with $3,623.94
  3.  GBC DocuBind TL300 Electric Binding System with $1,910.59
  ##### 3 Products with the highest profit in India
  1. Sauder Classic Bookcase, Traditional with $2,419.65
  2. Cisco Smart Phone, with Caller ID with $1,609.38
  3. Hamilton Beach Refrigerator, Red with $1,440.24
  ##### 3 Products with the highest profit in China
  1. Sauder Classic Bookcase, Metal with $1,463.07
  2. Bush Classic Bookcase, Mobile with $1,220.52
  3. HP Copy Machine, Color with $1,196.13

- ####  Identify the 3 subcategories with the highest average shipping cost in the United States.

  ##### The 3 subcategories with the highest average shipping cost in the United States are:
  1. Copiers with $165.29
  2. Machines with $132.24
  3. Tables with $69.95

- ####  Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African countries?  

![Assessing Nigeria's Profitability](nigeria-profitability.PNG)

In 2014, Nigeria had lowest total sales and profit compared to leading African countries with the most profit like South Africa, Morocco, Egypt and Democratic Republic of Congo. According to the visual, while Zimbabwe also made a loss, Nigeria lost the most money in the African region.

- #### (b) What factors might be responsible for Nigeria’s poor performance?

Factors that might be responsible for Nigeria's poor performance are:
1. Average Shipping Cost: $6.8
2. Average  Discount: $0.7
Compared to other countries, Nigeria's average shipping cost and discount is relatively higher.This could be why Nigeria is losing so much money instead of making profits.

- ####  Identify the product subcategory that is the least profitable in Southeast Asia. For this analysis, i sorted the top 3 least profitable product subcategory in SE Asia.

  Tables generated the highest loss among all other product categories in Southeast Asia.
  
- #### b) Is there a specific country in Southeast Asia where Global Superstore should stop offering the subcategory identified from the result above? For this analysis, i sorted the top 3 countries in Southeast Asia where Global Superstore should stop offering this subcategory.

  Global Superstore should stop offering the subcategory Tables in Indonesia. They generated the most losses for this subcategory.

- ####  Which city is the least profitable (in terms of average profit) in the United States?
- ####  b) Why is this city’s average profit so low? For this analysis, i sorted the top 3 least profitable cities in the US.

  The city which is least profitable in terms of average profit in the United States is Lancaster city with an average of -$157.
  Lancaster city's average profit is low because they make so much loss when they purchase echnology products.

- #### Which product subcategory has the highest average profit in Australia?  For this analysis, i sorted the top 3 product subcategory with the highest average profit.

  The product subcategory with the highest average profit in Australia is:
  1. Appliances with $139
  Followed by Copier with $105 and Phones with $98.

- #### Who are the most valuable customers and what do they purchase?
  
  ![Top Customers](top-customer.PNG)
  
  The top 3 valuable customers are:
  1. Tamara Chand
  2. Raymond Buch
  3. Hunter Lopez
  They all purchased Canon imageCLASS 2200 Advanced Copier.

## Conclusion/Recommendation

Based on the insights, here are actionable recommendations for improving business performance:
1. Offer exclusive discounts to retain top customers and encourage repeat purchases.
2. Reduce high shipping cost and overuse of discounts in Nigeria
3. Focus on high performing products, increase marketing for high demand products like Canon imageCLASS 2200 Advanced Copier.
4. Improve underperforming categories e.g Tables. Adjust pricing strategies to improve profitability.
