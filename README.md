PowerBI project

**Project 1 Title-Sales Analysis Report**

The Objective of the Sales Dashboard / Business Problem

The objective of the report is to analyze and present comprehensive insights into sales, profit, orders, profit margin, and various comparisons. It aims to provide a clear understanding of key performance indicators and trends using Power BI. The report objectives can be summarized as follows:

1.Calculate Total Sales: Calculate and display the total sales value for the selected period, allowing users to understand the overall revenue generated.

2.Calculate Profit: Calculate and visualize the total profit achieved based on the sales data, providing insights into the financial performance.

3.Analyze Orders: Analyze the number of orders placed during the selected period, helping to identify sales patterns and order trends.

4.Calculate Profit Margin: Calculate and visualize the profit margin percentage, enabling users to assess the profitability of products or services.

5.Compare Sales by Product with Previous Year: Compare sales performance for each product between the selected period and the previous year, highlighting growth or decline in sales.

6.Compare Sales by Months with Previous Year: Compare sales performance across different months between the selected period and the previous year, identifying regions with significant changes.

7.Display Top 5 Cities: Present a visualization showcasing the top 5 cities based on sales, allowing users to quickly identify the most lucrative locations.

8.Compare Profit by Channel with Previous Year: Compare profit generated by each channel between the selected period and the previous year, indicating improvements or challenges in profitability.

9.Analyze Sales by Customer and Compare with Previous Year: Analyze sales data by customer, highlighting the performance of individual customers and comparing it to the previous year.

10.Create Slicers for Date, City, Product, and Channel: Enable users to interact with the data by providing slicers for selecting specific dates, cities, products, and channels, allowing for dynamic filtering
and personalized analysis.

  Steps to follow for an end-to-end Power BI Project
  
  1.Gather Data
  
    Collect the necessary data for your project. This could include data from various sources such as databases, spreadsheets, or web services. Ensure the data is accurate and relevant to your objective.
     

  2.Power Querry – Data Extract, Transform & Load
  
    Power Query Editor in Power BI is a powerful tool for data cleaning and transformation. We will use it Clean and transform the data to make it suitable for analysis. This may involve removing duplicates, handling missing values, merging datasets, or creating calculated columns.
    
  3.Create a Date Table
  
    To work with Data Analysis Expressions (DAX) time intelligence functions, there’s a prerequisite model requirement: You must have at least one date table in your model.

  4.Create Data Model in Power BI Desktop
  
    Design and create a data model that represents the relationships between different tables in your data. Establish proper relationships, define keys, and establish hierarchies if needed. This step is crucial for accurate analysis and visualization
    

  5.Develop Reports in Power BI Desktop
  
    Use the Power BI Desktop application to create reports based on your data model. Add visualizations such as charts, tables, and maps to represent the data effectively. Apply filters, slicers, and drill-through functionalities to allow users to interact with the data.

    Create Report Background in PowerPoint
    Create Slicers – Date, City, Product, and Channel
    Create Dax measures
    Create Visuals:
    1.Sales By Product and Comparing it with last year’s Sales.
    
    2.Sales By Month and Comparing it with last year’s Sales.
    
    3.Sales of top 5 Cities
    
    4.Compare Profit by channel with Previous year’s Profit
    
    5.Sales By Customer and Comparing it with last year’s Sales
    
    6.Create Cards for Sales, Profit, Profit Margin & Product Sold
    
    7.Implementing DAX Calculations
    
      We will use Data Analysis Expressions (DAX) to create calculated columns, measures, and calculated tables to perform complex calculations and aggregations. DAX is a powerful formula language that allows you to manipulate data within Power BI.

      

    //Measures Total Sales
      Sales = SUM(Sales_Data[Sales])

    //Measures Previous Year Toal Sales
      Sales PY = CALCULATE([Sales], SAMEPERIODLASTYEAR(DateTable[Date]))

    //Diffrence Between Current Year Sales & Previous Year Sales
      Sales vs PY = [Sales] - [Sales PY]

    //Percentage Increase or Decrease in sales year on year (YOY%)
    
      Sales vs py % = DIVIDE([Sales vs PY],[Sales],0)
      
    >> Products Sold = SUM(Sales_Data[Order Quantity])
    
    >> Profit = SUM(Sales_Data[Profit]) 
    
    >> Profit LY = CALCULATE([Profit], SAMEPERIODLASTYEAR(DateTable[Date]))
    
    >> Pro    fit Vs LY = [Profit]- [Profit LY]
    
    >> Profit vs LY % = [Profit Vs LY]/[Profit]
    
    >> Profit Margin = DIVIDE([Profit],[Sales],0)
    
    >> Total Cost = SUM(Sales_Data[Total Cost]) 
    
    Conclusion of Power BI Sales Dashboard Project
    
    Conclusion for the year 2019:

    1.Sales decreased by more than 10%
    
    2.There is a drop in sales of all the top 7 Products
    
    3.Customers are leading to a drop in sales
    
    4.The profit margin in the Export channel is higher

**Project 2 Title-Accident on Road Analysis**   
 ## Project Overview        
The purpose of this Power BI dashboard is to analyze road accident data and identify patterns and trends that can help 
improve road safety. First step is to Import the data into Power BI and clean it to ensure it was accurate and ready for analysis. The data includes information about accidents, such as the number of vehicles involved, severity of the accident, and the location and time of the accident.
<img src="https://i.ibb.co/JB87dM8/Road-Accident-Analysis.jpg" alt="Road-Accident-Analysis" border="0">  

## Higlights of the Analysis      
Clients wants to create a Road Accident Dashboard for year 2021 and 2022 so that they can have insight on the below requirements-

- Primary KPI - Total Casualties and Total Accident values for Current Year(CY) and YoY growth

- Primary KPI's — Total Casualties by Accident Severity for Current Year and YoY growth

- Secondary KPI's - Total Casualties with respect to vehicle type for Current Year

- Monthly trend showing comparison of casualties for Current Year and Previous Year (PY)

- Casualties by Road Type for Current year

- Current Year Casualties by Area/ Location & by Day/ Night

- Total Casualties and Total Accidents by Location    

## ata Analysis Expressions (DAX) Formulas Used in Measures     

1.Total Casualties For Current Year and Year on Year Growth

(a) Current Year To Date Casualties -- CY Casualties Measure

CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])

(b) Previous Year Casualties -- PY Casualties Measure

PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))

(c) Year on Year Growth of Casualties - YoY Casualties Measure

YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]

2. Total Accidents for Current Year and Year on Year Growth
   
(a) Current Year Accidents Count -- CY Accidents Count Measure

CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])

(b) Previous Year Accidents Count -- PY Accidents Count Measure

PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))

(c) Year on Year Growth of Accidents - YoY Accidents Measure

YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]   

## Key findings      
-  Total Current(CY) Casualties-196k   
-  Total Year Over Year(YOY) Accidents-144k    
-  Current Year(CY)Fatal Casualties-2.9k     
-  Current Year(CY)Serious Casualties-27k      
-  Current Year(CY)Slight Casualties-165.8k

  ## Casualties in the Urban/Rural Areas        
  <img src="https://i.ibb.co/qJbtD4C/Casualties-By-Urban-Rural-Areas.jpg" alt="Casualties-By-Urban-Rural-Areas" border="0">       
  This indicates that there are more casualties in the urban area than in the rural areas 
  
 ## Casualties By Vehicle           
  <img src="https://i.ibb.co/mSQHyzM/Casualties-By-Vehicle-Type.jpg" alt="Casualties-By-Vehicle-Type" border="0">     
  Car recorded the highest number of casualties with a total of 155804     

## Current-Year-vs-Previous-Year-Casualties-Monthly-Trend       
<img src="https://i.ibb.co/HYzdGjK/Current-Year-vs-Previous-Year-Casulaties-Monthly-Trend.jpg" alt="Current-Year-vs-Previous-Year-Casulaties-Monthly-Trend" border="0">             

November recorded the highest number of casualties with a record of 20975 in 2021 as compared with 18489 in 2022.   

# Project 3-SuperStore Sales Analysis  
## Project Objectives    
To contribute to the success of the business by Utilizing data analysis techniques,specifically focusing on time series analysis
to provide valuable insights and accurate sales forecasting.        
The objectives can be broken down into  the following detailed components;    
-  Dashboard Creation-Identify KPIs ,design an intuitive and visually appealing dashboard,add interactive  visualizations and filtering
  capabilities to allow users  to explore  the data at various levels of granualarity
-  Data Analysis-Provide valuable insights to business entities regarding the effectiveness of their sales strategies through visualizations and charts
-  Sales Forecasting-Leverage historic data  and apply time series analysis to generate sales forecast for the next 15 days
-  Actionable Insights and Recommendation-End goal is to derive insights  and actionable information that can drive strategic decision-making, support the supermarket's goals for growth,efficiency and customer satisfaction.





  
  
  
  
  
 

  

🚀 About Me
5 years of Industry experience as a data analyst and 2 years as a Data Scientist using Machine Learning algorithms. I have consistently interfaced with SQL, PowerBI and Tableau. I have work experience and extensive knowledge in Python with libraries such as Sklearn, TensorFlow, Pandas, NumPy, Matplotlib, seaborn. Identifying business needs and developing valuable solutions to improve accuracy and process optimization.

Hi, I'm Oyekan
👋

🔗 Links
portfolio linkedin

Other Common Github Profile Sections
👩‍💻 I'm currently working on more SQL projects and Data Science Projects

🧠 I'm doing a Postgraduate program at British Computer Society(BCS)

👯‍♀️ I'm looking to collaborate with other developers

📫 You can reach me on +2348038549476

🛠 Skills
Advanced Excel SQL Tableau PowerBI Python Programming Numpy,pandas,scipy etc...


Installation
Install my-project with npm

  npm install my-project
  cd my-project
