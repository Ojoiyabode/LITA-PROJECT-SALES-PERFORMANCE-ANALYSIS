# LITA-CAPSTONE PROJECT:SALES-PERFORMANCE-ANALYSIS FOR A RETAIL STORE
---
A repository of the sales performance data of retail store showing key insights and making data-driven decisions from the insights discovered from the data.

## TABLE OF CONTENT
---


## PROJECT OBJECTIVE
---
- To analyze the sales performance of the retail store by uncovering key insights such as - Top-selling products - Regional performance - Monthly sales trend - Average saes per product and total revenue by region using Excel and SQL server environment.
- Create interactive Dashboards that highlight these findings using Excel and PowerBi.

## DATA SOURCE
---
The data used was gotten from the tutors of Ladies in Tech program for exploration and analysis as a prerequisite for the certification.
- <a href = "https://github.com/Ojoiyabode/LITA-PROJECT-SALES-PERFORMANCE-ANALYSIS/blob/main/LITA%20Capstone%20Dataset%20-%20Copy.xlsx">LITA CAPSTONE SALES DATASET</a>

## TOOLS USED
---
- Microsoft Excel for data exploration, cleaning and transforming
- SQL (Structured Query Language) for querying and analysing data in relational database
- Powerbi for visualization and building interactive dashboards

## QUESTIONS (KPIs)
---
1. Excel: Perform an initial exploration of the sales data. Use pivot tables to summarize total sales by product, region and month. Use Excel formulas to calculate metrics such as average sales per product and total revenue by region. Create any other interesting report.

2. Structured Query Language (SQL): - Retrieve the total sales for each product category, - Find the number of sales transactions in each region, - Find the highest-selling product by total sales value, - Calculate total revenue per product, - Calculate monthly sales totals for the current year 2024, - Find the top 5 customers by total purchase amount, - Calculate the percentage of total sales contributed by each region, - Identify products with no sales in the last quarter.

3. Power BI : Create a dashboard that visualises the insights found in Excel and SQL. It should include a sales overview, top performing products and regional breakdowns.
   

 ## DATA CLEANING AND PREPARATION PROCESS
 ---

 ### EXCEL
- The data was explored to check for missing values and outliers that could affect the analysis.
-  Data duplicates including empty cells and spaces were removed. Date formats were also checked to ensure that the data is consistent.
- After the data had been thoroughly cleaned and validated for analysis. The data was summarized using pivot table according to the questions asked. 
- Used Excel formulas to calculate metrics such as average sales per product and total revenue by region
 
 
 ### EXCEL REPORT
 #### USING EXCEL - TOTAL SALES BY REGION, PRODUCTS AND MONTHS

 ![Screenshot 2025-02-24 115309](https://github.com/user-attachments/assets/0ebf8eaa-2a1e-41c7-8b78-a31284dc5dc5)


 #### TOTAL SALES BY PRODUCT
 
![Screenshot 2025-02-25 130423](https://github.com/user-attachments/assets/06392e5f-04ad-45bf-8be2-39beb00e1f14)

#### TOTAL SALES BY REGION

![Screenshot 2025-02-25 170219](https://github.com/user-attachments/assets/037f920c-13f2-4644-8492-672e7e2be29b)

  #### OVERALL TOTAL PRODUCT SALES PER REGION

 ![Screenshot 2025-02-25 180555](https://github.com/user-attachments/assets/d50d46fd-1ea2-4c83-8213-4e5ea6940093)

#### TOTAL SALES PER MONTH

![Screenshot 2025-02-25 190525](https://github.com/user-attachments/assets/e21fb15c-f6ae-4bae-a15d-71e0a0788702)


  #### AVERAGE SALES PER PRODUCT
                         
![Screenshot 2025-03-11 090724](https://github.com/user-attachments/assets/cb9c2864-7737-44e3-a9f2-86a8178fee31)


  #### TOTAL REVENUE BY REGION
  
  ![Screenshot 2025-03-11 090740](https://github.com/user-attachments/assets/880afad4-6b6a-43b0-b37b-2561ab89f6ec)


 ### SQL- STRUCTURED QUERY LANGUAGE
 This is where I included basic lines of queries used during analysis
 
 ##### CREATE DATABASE
 `create database LITA_CAP
SELECT * FROM [dbo].[SalesData$]`

##### TO VIEW THE TABLE
 `SELECT [OrderID], [Customer Id], [Product], [Region], [OrderDate], [Quantity], [Unitprice], [Total Sales]
from [dbo].[SalesData$]
order by OrderId asc`

##### SUM OF TOTAL SALES
`SELECT SUM([Total Sales]) AS Total_Sales_shirt
FROM [dbo].[SalesData$]`
- Total_Sales = 2101090
  
 ##### TOTAL SALES PER PRODUCT CATEGORY
`SELECT SUM([Total Sales]) AS Total_Sales_shirt
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Shirt'`
- Total_Sales_shirt = 485600

  `SELECT SUM([Total Sales]) AS Total_Sales_shoes
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Shoes'`
- Total_Sales_shoes = 613380

  `SELECT SUM([Total Sales]) AS Total_Sales_Hat
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Hat'`
- Total_Sales_Hat = 316195
  
`SELECT SUM([Total Sales]) AS Total_Sales_Socks
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Socks'`
- Total_Sales_Socks = 180785
  
`SELECT SUM([Total Sales]) AS Total_Sales_Gloves
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Gloves'`
- Total_Sales_Gloves = 296900

`SELECT SUM([Total Sales]) AS Total_Sales_Jacket
FROM [dbo].[SalesData$]
WHERE [PRODUCT] = 'Jacket'`
- Total_Sales_Jacket = 208230

##### HIGHEST SELLING PRODUCT BY TOTAL SALES
`SELECT TOP 1 [PRODUCT], SUM([Total Sales]) AS HIGHEST_SELLING_PRODUCT
FROM [dbo].[SalesData$]
GROUP BY [PRODUCT]
ORDER BY SUM([Total Sales]) DESC`
- HIGHEST_SELLING_PRODUCT = Shoes at 613380

##### TOTAL REVENUE PER PRODUCT
`SELECT TOP 1 [PRODUCT], SUM([Total Sales]) AS HIGHEST_SELLING_PRODUCT
FROM [dbo].[SalesData$]
GROUP BY [PRODUCT]
ORDER BY SUM([Total Sales]) DESC`
- Shoes	613380
- Jacket 208230
- Hat	316195
- Socks	180785
- Shirt	485600
- Gloves 296900

##### MONTHLY SALES TOTAL FOR THE CURRENT YEAR(2024)
`SELECT
MONTH([OrderDate]) AS OrderMonth,
SUM([Total Sales]) AS Total_Sales_for_2024
FROM
[dbo].[SalesData$]
WHERE
YEAR([OrderDate]) = 2024
GROUP BY
MONTH([OrderDate])
ORDER BY
OrderMonth ASC`

1.   198400- JAN
2.   298800 -FEB
3.  54780 -MARCH
4.  39440 -APRIL
5.  44640-MAY
6.  148200 -JUNE
7.  37200 -JULY
8.  174300 -AUGUST 


##### TOP 5 CUSTOMERS BY TOTAL PURCHASE AMOUNT
`SELECT TOP 5
[Customer Id] AS Top5_Customer,
SUM([Total Sales]) AS Total_Sales
FROM
[dbo].[SalesData$]
GROUP BY
[Customer Id]
ORDER BY
Total_Sales DESC`

- TOP 5 CUSTOMERS =	- Cus1302 4235
			- Cus1431 4235
		        - Cus1250 4235
		        - Cus100 4235
			- Cus1115 4235

##### PERCENTAGE OF TOTAL SALES BY EACH REGION
`SELECT 
    [Region],
    SUM([Total Sales]) AS Total_Sales,
    (SUM([Total Sales]) / (SELECT SUM([Total Sales]) FROM [dbo].[SalesData$])) * 100 AS Sales_Percentage
FROM 
    [dbo].[SalesData$]
GROUP BY 
    [Region]
ORDER BY 
    Sales_Percentage DESC`
    
    Sales_Percentage by Region =
 - South -	927820  -	44.1589841463241
 - East -	485925  -        23.1272815538601
 - North -     387000    - 	18.4190110847227
 - West -	300345  -	14.2947232150931

##### PRODUCTS WITH NO SALES IN THE LAST QUARTER

  `SELECT [PRODUCT] AS No_Sales
	from [dbo].[SalesData$]
	WHERE ([Total Sales]) = 0 
	AND YEAR([OrderDate]) =2024
	AND MONTH([OrderDate]) > 9
	GROUP BY [PRODUCT]`

- PRODUCTS WITH NO SALE = NIL/ZERO

## PROJECT INSIGHTS
**From the excel report and SQL queries above, The following insights can be deduced;**

**The following insights can be gotten from the** **TOTAL SALES BY PRODUCT**

- Top selling product: Shoes are the highest selling product with a total sales of 613,380. This indicates a great demand for the product.

- Least selling product: Socks are the least selling product with a total sales of 180,785 which indicates less demand for the product.

 - Overall Total Sales Performance by Product
Total Sales of all products (Shoes, Shirts, Hat, Gloves, Jacket, Socks) equaled a total of 2,101,090 which indicates a positive market response. Socks is the least selling product, this implies that the product require more marketing strategies for product visibility or the product has less target aundience.

**The following insights can be deduced from the TOTAL SALES BY REGION**

- East: Shirt is the top selling in the East region at 49% (237,600) while shoes is the least seling product at 8% (32,200). Hat and Jacket have a total sales of 43% (211,125).

- North: Shirt is the top selling product in the North region at 64% (248,000), while Hat is the least selling product at 8% (34,720)

- South: Shoes are the top selling product in the South region at 59% (546,300) while Socks is the least selling product at 14% (133,920)

- West: Hat is the top selling product in the West region at 58% (174,300) while shoes are the least selling product at 10% (29,800)

**The following insight can be deduced from OVERALL PRODUCT SALES BY REGION**

  - Top performing Region : The South is the overall top performing Region, It has the highest overall sales performance of 44% (927,820). This is followed by the East region at 23% and the North region at 18%.
  - Lowest Performing Region : Then West region has the lowest overall sales performance at 14% (300,345)

**The following insight can be deduced from the above TOTAL SALES PER MONTH**

- Peak sales : There were remarkable peak sales in February 2023, July 2023 and February 2024. These peak sales shows that these periods were months of high product demand.

- Low Sales period : The lowest sales was recorded in April 2023 where there was a notable drop in sales.
  





  
 ### POWER BI DASHBOARD
 
 ## RECOMMENDATION
 - FROM THE TOTAL SALES PER PRODUCT: Socks is the least selling product, this implies that the product require more marketing strategies for product visibility or the product has less target aundience.
   
 - FROM THE TOTAL SALES PER REGION: It is recommended that the target audience for the least selling products per region should be re-evualted so marketing strategies can be done targeting the target audience for these products so there can be an increase in product visibility and sales for these product.

 
