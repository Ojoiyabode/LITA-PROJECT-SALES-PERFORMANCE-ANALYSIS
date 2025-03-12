# LITA-CAPSTONE PROJECT:SALES-PERFORMANCE-ANALYSIS
A repository of the sales performance data of retail store showing key insights and making data-driven decisions from the insights discovered from the data.

## TABLE OF CONTENT

## PROJECT TITLE : SALES PERFORMANCE ANALYSIS OF A RETAIL STORE

## PROJECT OBJECTIVE
---
The objective of this project is to uncover the following Key Sales performance insights which includes;
### Insights to look out for
- Top-selling products
- Regional performance
- Monthly sales trend
- Average saes per product and total revenue by region
- Extract key insights using SQL server environment

### Goals
- Create visuals that captures these findings using PowerBi dashboard
- Give data-driven recommendations 

## DATA SOURCES
The data used was gotten from the tutors of Ladies in Tech program for exploration and analysis as a prerequisite for the certification.

## TOOLS USED
- Microsoft Excel for data exploration, cleaning and transforming, analysis
- SQL (Structured Query Language) for querying and analysing data in relational database
- Powerbi for visualization and building interactive dashboards

 ## DATA CLEANING AND PREPARATION

 ### EXCEL
 The data was gotten from the Ladies in Tech program. The data was explored to check for missing values and outliers that could affect the analysis using Microsoft Excel, Data duplicates including empty cells and spaces were removed. Date formats were also checked to ensure that the data is uniform.
 After the data had been thoroughly cleaned and validated for analysis. The data was summarized using pivot table to analyse the total sales by product, month and region.
 Used Excel formulas to calculate metrics such as average sales per product and total revenue by region
 
 
 ## ANALYSIS & INSIGHTS 
 ## USING EXCEL - TOTAL SALES BY REGION, PRODUCTS AND MONTHS

 ![Screenshot 2025-02-24 115309](https://github.com/user-attachments/assets/0ebf8eaa-2a1e-41c7-8b78-a31284dc5dc5)


 ### INSIGHTS ON TOTAL SALES BY PRODUCT
![Screenshot 2025-02-25 130423](https://github.com/user-attachments/assets/06392e5f-04ad-45bf-8be2-39beb00e1f14)

 
The following insights can be gootten from the above
- Top selling product
  
  Shoes are the highest selling product with a total sales of 613,380. This indicates a great demand for the product.
- Least selling product

    Socks are the least selling product with a total sales of 180,785 which indicates less demand for the product.

 - Overall Total Sales Performance by Product
Total Sales of all products (Shoes, Shirts, Hat, Gloves, Jacket, Socks) equaled a total of 2,101,090 which indicates a positive market response. Socks is the least selling product, this implies that the product require more marketing strategies for product visibility or the product has less target aundience.

### INSIGHTS ON TOTAL SALES BY REGION
### Total Product sales per region

![Screenshot 2025-02-25 170219](https://github.com/user-attachments/assets/037f920c-13f2-4644-8492-672e7e2be29b)

The following insights can be deduced from the above 

- East: Shirt is the top selling in the East region at 49% (237,600) while shoes is the least seling product at 8% (32,200). Hat and Jacket have a total sales of 43% (211,125).

- North: Shirt is the top selling product in the North region at 64% (248,000), while Hat is the least selling product at 8% (34,720)

- South: Shoes are the top selling product in the South region at 59% (546,300) while Socks is the least selling product at 14% (133,920)

- West: Hat is the top selling product in the West region at 58% (174,300) while shoes are the least selling product at 10% (29,800)


  ### Overall Total Product sales per region

 ![Screenshot 2025-02-25 180555](https://github.com/user-attachments/assets/d50d46fd-1ea2-4c83-8213-4e5ea6940093)

  The following insight can be deduced from the above

  - South region has the highest overall sales performance of 41% with its top selling product being Shoes, This is followed by the East region at 23% and the North region at 18%. The East and North region highest selling product being Shirt. Then West region has the lowest overall sales performance at 14% with its top sellng product being Hats.

### INSIGHTS ON TOTAL SALES PER MONTH

![Screenshot 2025-02-25 190525](https://github.com/user-attachments/assets/e21fb15c-f6ae-4bae-a15d-71e0a0788702)


The following insight can be deduced from the above:
- Peak sales : There were remarkable peak sales in February 2023, July 2023 and February 2024. These peak sales shows that these periods were months of high product demand.

- Low Sales period : The lowest sales was recorded in April 2023 where there was a notable drop in sales.

  ### AVERAGE SALES PER PRODUCT                         
![Screenshot 2025-03-11 090724](https://github.com/user-attachments/assets/cb9c2864-7737-44e3-a9f2-86a8178fee31)


  ### TOTAL REVENUE BY REGION
  ![Screenshot 2025-03-11 090740](https://github.com/user-attachments/assets/880afad4-6b6a-43b0-b37b-2561ab89f6ec)




 ### SQL- STRUCTURED QUERY LANGUAGE
 This is where I included basic lines of queries used during analysis
 create database LITA_CAP
 SELECT * FROM [dbo].[SalesData$]

 SELECT [OrderID], [Customer Id], [Product], [Region], [OrderDate], [Quantity], [Unitprice], [Total Sales]
from [dbo].[SalesData$]
order by OrderId asc

 TOTAL SALES PER PRODUCT CATEGORY
 

 
 
 ### POWERBI
 
 ## RECOMMENDATION
 - FROM THE TOTAL SALES PER PRODUCT: Socks is the least selling product, this implies that the product require more marketing strategies for product visibility or the product has less target aundience.
   
 - FROM THE TOTAL SALES PER REGION: It is recommended that the target audience for the least selling products per region should be re-evualted so marketing strategies can be done targeting the target audience for these products so there can be an increase in product visibility and sales for these product.

 
