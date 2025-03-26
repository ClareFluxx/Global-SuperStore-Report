# Global SuperStore Report

![Introduction](intro_photo.jpg)
---

## Introduction
This is a Power BI project on the sales analysis of an imaginary store called "Global SuperStore". The objective of this project is to analyze the dataset and provide answers to business questions.

**_Disclaimer_**: _All datasets and reports do not represent any company, institution, or country. It is just a dummy datatset used to demonstrate the capabilities of Power BI._

## Problem Statement

1.  What are the three countries that generated the highest total profit for Global Superstore in 2014? (b) For each of these three countries, find the three products with the highest total profit. Specifically, what are the products’ names and the total profit for each product?  
2. Identify the 3 subcategories with the highest average shipping cost in the United States.
3. Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African countries? (b) What factors might be responsible for Nigeria’s poor performance? You might want to investigate shipping costs and the average discount as potential root causes.  
4. Identify the product subcategory that is the least profitable in Southeast Asia.  Note: For this question, assume that Southeast Asia comprises Cambodia, Indonesia, Malaysia, Myanmar (Burma), the Philippines, Singapore, Thailand, and Vietnam. (b) Is there a specific country i n Southeast Asia where Global Superstore should stop offering the subcategory identified in 4a?  
5. Which city is the least profitable (in terms of average profit) in the United States? For this analysis, discard the cities with less than 10 Orders. (b) Why is this city’s average profit so low?  
6. Which product subcategory has the highest average profit in Australia?  
7. Who are the most valuable customers and what do they purchase?

 ## Skills/Concepts Demonstrated 
 
The following Power BI features where incorporated:
- Power Query (Data cleaning and transformation),
- Data Modeling,
- DAX,
- Data Presentation (Visualizations),
- Filters and Interactivity

## Data Modeling
![Data Modeling](data_modeling.PNG)
---

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

#### This project documentation contains screenshots of data visualization as a means to interpret and easily read results gotten from my analysis.

## Visual Overview

- #### What are the three countries that generated the highest total profit for Global Superstore in 2014?
  
  
  In 2014,the three countries that generated the highest total profit for global superstore are:
  1. United States with $93,507.5
  2. India with $48,807.6
  3. China with $46,793.9

- #### (b) For each of these three countries, find the three products with the highest total profit. Specifically, what are the products’ names and the total profit for each product?


































 
