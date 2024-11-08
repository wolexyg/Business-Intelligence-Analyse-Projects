# Power BI/Tableau Projects

# Project 1- Title-Sales Analysis Report        

The Objective of the Sales Dashboard / Business Problem

The objective of the report is to analyze and present comprehensive insights into sales, profit, orders, profit margin, and various comparisons. It aims to provide a clear understanding of key performance indicators and trends using Power BI.           
<img src="https://i.ibb.co/gD3F2mK/Sales-Dashboard.jpg" alt="Sales-Dashboard" border="0">            


The report objectives can be summarized as follows:

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

# Project 2 Title-Accident on Road Analysis  
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

## Data Analysis Expressions (DAX) Formulas Used in Measures     

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

# Insights           
## Accident Severity by Casualties Analysis        
<img src="https://i.ibb.co/nkPnMJq/Road-Accident-KPI-Banner.jpg" alt="Road-Accident-KPI-Banner" border="0">          
Accident Severity by Casualties Analysis entails a comprehensive evaluation of all factors contributing to the severity of accidents, particularly focusing on the number and extent of casualties involved. This analysis encompasses direct elements such as the nature of the accident and injuries sustained, as well as indirect factors like road conditions and environmental influences.          

## Casualties in the Urban/Rural Areas            
  <img src="https://i.ibb.co/qJbtD4C/Casualties-By-Urban-Rural-Areas.jpg" alt="Casualties-By-Urban-Rural-Areas" border="0">       
There is a higher risk of casualties in urban areas compared to rural areas. This is likely due to a combination of factors, including population density, traffic volume, and speed.    
  
 ## Casualties By Vehicle           
  <img src="https://i.ibb.co/mSQHyzM/Casualties-By-Vehicle-Type.jpg" alt="Casualties-By-Vehicle-Type" border="0">          
  Car recorded the highest number of casualties with a total of 155804.Insights on road fatalities by vehicle type reveal cars as the most lethal, likely due to their size, speed, and limited protection for cyclists. Bikes follow closely behind in fatalities. Trucks, driven by experienced professionals, are least involved in fatal crashes. Casualties vary based on factors like speed limits, road type, and safety features, such as airbags and seatbelts.                   

## Current-Year-vs-Previous-Year-Casualties-Monthly-Trend       
<img src="https://i.ibb.co/HYzdGjK/Current-Year-vs-Previous-Year-Casulaties-Monthly-Trend.jpg" alt="Current-Year-vs-Previous-Year-Casulaties-Monthly-Trend" border="0">               

November recorded the highest number of casualties with a record of 20975 in 2021 as compared with 18489 in 2022. The largest discrepancy between CY and PY casualties occurs in April and May, possibly attributed to seasonal factors like increased summer road traffic. However, due to the limited two-year dataset and significant month-to-month variation, drawing conclusive trends about overall casualty trends proves challenging.            
## Casualties By Light Conditions    
<img src="https://i.ibb.co/1f2gMJG/Casulaties-By-Light-Conditions.jpg" alt="Casulaties-By-Light-Conditions" border="0">         
People are more likely to be injured or killed in accidents that occur during daylight hours. This is likely due to a combination of factors, such as increased traffic volume, risky behaviors, and poorer visibility at night.        

## Casualties By Road Type    
<img src="https://i.ibb.co/1qJXg6g/Casualties-By-Road-Type.jpg" alt="Casualties-By-Road-Type" border="0">     
This findings underscore the importance of targeted interventions and resource allocation to enhance safety measures, reduce casualties, and improve overall road safety     

## Casualties By Location    
<img src="https://i.ibb.co/mTZkp0s/Casualties-By-Location.jpg" alt="Casualties-By-Location" border="0">     
The yellow dots represent the locations of accidents.           

## Recommendations   
-  By conducting a thorough assessment, stakeholders can better understand the dynamics of accidents, identify areas for improvement in safety measures, and implement targeted interventions to mitigate severity and enhance overall safety outcomes.   

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

  ## Tools Used    
  -  Microsoft Excel(Dataset)
  -  Power Query(For Data Cleaning)
  -  Microsoft PowerBI(Data Modelling,DAX Calculations,Dashboard Creation)  

 ## Dashboard Creation              
 <img src="https://i.ibb.co/s3SV3yH/Superstore-Sales-Dashboard4.jpg" alt="Superstore-Sales-Dashboard4" border="0">   


 
 
 ## Data Analysis     
 Questions to consider    
 -  Which region has the highest number of  Sales?      
   <img src="https://i.ibb.co/LQYpvy7/Sales-By-Region-Superstore.jpg" alt="Sales-By-Region-Superstore" border="0">
    The Western region is the highest selling region i.e sales 522k(33%)    
    


 -  Which Category has the highest number of sales?       
   <img src="https://i.ibb.co/BBNGtY9/Sales-By-Category-Superstore.jpg" alt="Sales-By-Category-Superstore" border="0">

   Office Supplies has the highest number sales.           

 -  Which is the top selling product Category and Subcategory?.               
   <img src="https://i.ibb.co/BBNGtY9/Sales-By-Category-Superstore.jpg" alt="Sales-By-Category-Superstore" border="0">         
    Office Supplies are the top selling Product Category                                         

   <img src="https://i.ibb.co/XDBrDr3/Sales-By-Sub-Category-Superstores.jpg" alt="Sales-By-Sub-Category-Superstores" border="0">        
    Phones are the top selling Subcategory

 -  Which is the preferred ship mode?.                  

    <img src="https://i.ibb.co/k1vyRR6/Sales-By-Ship-mode-Superstore.jpg" alt="Sales-By-Ship-mode-Superstore" border="0">      
    
    Standard Class is the prefered ship mode.

-  Which Segment recorded the highest sales?         
    <img src="https://i.ibb.co/TrXyz8d/Sales-By-Segment-Superstore.jpg" alt="Sales-By-Segment-Superstore" border="0">
   
   Consumers recorded the highest sales of 753k

  ## Sales Forecasting              
  <img src="https://i.ibb.co/vxCmPF9/Sales-Forecast-Superstore.jpg" alt="Sales-Forecast-Superstore" border="0">              



  ## Actionable Insights     
  -  Consumers contributed to more than half of the Superstores revenue
  -  The most preferred Shipping mode is the Standard Class
  -  Most valuable product is the Office Supplies
  -  Phones are the top selling product Subcategory
  -  California has the highest number of sales
  -  The Western Region emerged as the highest selling region

  ## Recommendations          
  -  Consumer and Corporate segment make up more than 70% of the Customer base segments
  -  Fresh marketing and promotional campaigns to target specific regions with higher sales potential by introducing special promotions and discounts.     
  -  Allocate resources to optimize top performing product categories and subcategories to maximize sales
  -  For least selling products,consider to either drop them from the catalogue or change suppliers and bargain for cheaper price.
  -  We can consider offering multiple shipping options to cater for different customer preferences.


# Project 4-Sales Data Analysis      
## Project Objective 
The Objective of this Analysis is to gain valuable insight that will propel actionable insights and inform the company's strategic decisions. The impact of this analysis on the business and the final outcome.         

<img src="https://i.ibb.co/rdf6LTz/Sales-Analysis-data.jpg" alt="Sales-Analysis-data" border="0">   

The Project can be broken down based on the needs of the stakeholders into;  
- Key Findings-Summary of the sales
- Actionable Insights
- Impact on Business      
- Proposed Strategic Actions     
- Recommendation        
- Conclusion          

## Tools used         
- Microsoft Excel(dataset)
- Power Query(for Data Cleaning)      
- Microsoft Power BI(Data Modelling,DAX Calculation and Dashbard Creation)

## Key Findings
-  The total sales across the years amount to 140.92 Million naira  from 2022 to 2024.
-  Benin has emerged as the top performing region contributing to 42.03 Million
   Naira to the total sales.     
-  Additionally,Quarter 4 stands out as the highest selling quarter with 35.69 Million naira in sales across the years.
-  Product E emerged as the best selling product across all regions with 28.4 million naira in sales.

  ## Sales By Year    
  <img src="https://i.ibb.co/2kLbfx4/Total-Sales-over-years.jpg" alt="Total-Sales-over-years" border="0">  
  The above line chart shows the Sales by year indicating an overall upward sales trend from 2022 to 2024.    

  ## Top Performing Region      
  <img src="https://i.ibb.co/KqsKZ0Y/Sales-By-Region-Sales.jpg" alt="Sales-By-Region-Sales" border="0">       
  The bar Chart highlights sales by region with Benin as the top performing region with a total sales of 42.03 Million naira.         

  ## Quarterly Sales Performance   
  <img src="https://i.ibb.co/Mkc6Xf9/Total-Sales-Over-Quarter.jpg" alt="Total-Sales-Over-Quarter" border="0">      

  ## Top Product Performance     
  <img src="https://i.ibb.co/cLRVbNs/Sales-By-Product.jpg" alt="Sales-By-Product" border="0">       
  Product E is the highest selling product achieving a total sales of 28.4 Million Naira across all the regions. This indicates  a strong preference and Market demand for Product E in all the regions.  
  
 ## Daily Sales Performance     
 <img src="https://i.ibb.co/wYWmg43/Total-Sales-By-Day.jpg" alt="Total-Sales-By-Day" border="0">   
 This line chart shows that there are more sales on weekends than on weekdays.    

 # Actionable Insights    
 - From our analysis, it is evident that Benin is a critical market contributing nearly 30% to our total sales.
 - Quarter 4 consistently emerges as the most lucrative period likely due to seasonal factors.
 - Product E came top as the best selling product across all regions indicating a strong preference of this product above all the other product.
 - Sales are significantly higher on Weekends compared to weekdays, suggesting that customers are likely to make more purchase during the weekend.

## Impact on Business    
-  Implementing these recommendations can significantly boost our overall sales and revenue.
-  By establishing dominance in key regions like Benin, we cam position ourselves as a market leader
-  Improved forecasting and resource allocation based on sales trend will also enhance our operational efficiency
-  Success in Benin can be used as a model for expanding into similar markets, potentially uncovering new revenue streams.
-  Enhanced marketing and targeted strategies can attract new customers and retain existing ones, leading to sustainable business growth.

    

## Proposed Strategic Actions    
I propose two strategic actions;    
-  Firstly, expand our presence in Benin by increasing our marketing budget and sales team.
-  Secondly, enhance our Quarter 4 readiness by developing targeted promotions and ensuring adequate inventory levels.

## Recommendations    
-  Based on this analysis, I will recommend focusing on Benin by enhancing our marketing and sales efforts.
-  Additionally, we can also optimize our Quarter 4 strategies by strengthening our campaigns and managing inventory efficiently to maximize sales during the peak period. We can also investigate the strategies and market conditions that have led to the increase  of sales in Benin and Quarter 4.,then apply these insights to other regions and quarters to elevate the overall sales performance.
-  Given the strong performance of Product E across all regions, allocate more marketing resources to promote Product E.
-  Optimizing Weekend Strategies: We can implement special promotions, discounts or events on weekends to capitalize on higher foot traffic and sales. This can further boost weekend sales across all products lines.


## Conclusion    
In conclusion, by leveraging these insights and implementing the recommended strategies, the business can enhance its market position, drive revenue growth, and improve operational efficiency, leading to a better overall business outcomes.     

## Project 5-Car Sales Analysis       
## Project Overview    
Our company is a car dealership that sells various car models. To effectively track and analyse our sales performance, we need a comprehensive Car Sales Dashboard in Power BI.     
<img src="https://i.ibb.co/Bqzvnvz/Car-Sales-Dashboard-pic.jpg" alt="Car-Sales-Dashboard-pic" border="0">         
<img src="https://i.ibb.co/Q6myxfD/Car-Sales-Dashboard-pic2.jpg" alt="Car-Sales-Dashboard-pic2" border="0">            

## Objectives     
The objective of this project is to design and develop a dynamic and interactive Car Sales Dashboard using Power BI. The dashboard will visualize critical KPIs related to our car sales, helping us understand our sales performance over time and make data-driven decisions.  
## Problem Statement 1: KPI’s Requirement          
The dashboard should provide real-time insights into key performance indicators (KPIs) related to our sales data. This will enable us to make informed decisions, monitor our progress, and identify trends and opportunities for growth.        
## 1.	Sales Overview:               
•	Year-to-Date (YTD) Total Sales        
•	Month-to-Date (MTD) Total Sales           
•	Year-over-Year (YOY) Growth in Total Sales           
•	Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales           
## 2.	Average Price Analysis:         
•	YTD Average Price        
•	MTD Average Price        
•	YOY Growth in Average Price              
•	Difference between YTD Average Price and PTYD Average Price        
## 3.	Cars Sold Metrics:                     
•	YTD Cars Sold         
•	MTD Cars Sold        
•	YOY Growth in Cars Sold          
•	Difference between YTD Cars Sold and PTYD Cars Sold   

## Problem Statement 2: Charts Requirement     
-  YTD Sales Weekly Trend: Display a line chart illustrating the weekly trend of YTD sales. The X-axis should represent weeks, and the Y-axis should show the total sales amount.      
-  YTD Total Sales by Body Style: Visualize the distribution of YTD total sales across different car body styles using a Doughnut Chart.            
- 	YTD Total Sales by Color: Present the contribution of various car colors to the YTD total sales through a Doughnut chart.           
-  YTD Cars Sold by Dealer Region: Showcase the YTD sales data based on different dealer regions using a map chart to visualize the sales distribution geographically.            
-  Company-Wise Sales Trend in Grid Form: Provide a tabular grid that displays the sales trend for each company. The grid should showcase the company name along with their YTD sales figures.           
-  Details Grid Showing All Car Sales Information: Create a detailed grid that presents all relevant information for each car sale, including car model, body style, colour, sales amount, dealer region, date, etc

  ## Insights    
  ## YTD Sales Weekly Trend   
  <img src="https://i.ibb.co/7WFQgT3/YTD-Sales-Weekly-trend.jpg" alt="YTD-Sales-Weekly-trend" border="0">      


  ## YTD Total Sales By Body Style     
  <img src="https://i.ibb.co/YP20tyn/YTD-Total-Sales-By-Body-Style.jpg" alt="YTD-Total-Sales-By-Body-Style" border="0">        

  ## YTD Total Sales By Color     
  <img src="https://i.ibb.co/YZhkTv4/YTD-Total-Sales-By-Color.jpg" alt="YTD-Total-Sales-By-Color" border="0">         

  ## YTD Cars Sold By Dealer Region          
  <img src="https://i.ibb.co/p0pbWPd/YTD-Total-Sales-By-Dealer-Region.jpg" alt="YTD-Total-Sales-By-Dealer-Region" border="0">     

  ## Company-Wise Sales Trend     
  <img src="https://i.ibb.co/ssXrrp2/Company-wise-Sales-Trend.jpg" alt="Company-wise-Sales-Trend" border="0">       

  ## Details Grid Showing All Car Sales Information      
  <img src="https://i.ibb.co/QYBhCQv/Car-Sales-Details.jpg" alt="Car-Sales-Details" border="0">      

  ## Key Findings               
  -  Strong YOY Sales Growth: The company achieved a 23.59% increase in year-over-year (YOY) sales, with YTD total sales reaching $371.2 million, a difference of $70.8 million from the previous year.
  -  High MTD Sales Performance: Monthly-to-date (MTD) total sales are $54.2 million, indicating strong sales momentum for the current month.     
  -  Slight Decrease in Average Price: The YTD average price per car is $28,000, showing a minor decline from the prior year’s average of 0.22 thousand, a YOY drop of 0.79%.
  -  Notable Increase in Cars Sold: The number of cars sold YTD is 13.3 thousand, an increase of 2.6 thousand compared to last year, reflecting a 19.73% YOY increase.
  -  Stable MTD Average Price: The MTD average price is $28.26 thousand, showing relatively steady pricing.

## Actionable Insights  
-  Sales Expansion: With sales growth above 20% YOY, further investment in high-performing sales regions or digital channels can capitalize on the current momentum.       
-  Pricing Adjustments: Despite the high sales volume, the slight drop in average price suggests potential room for improved pricing strategies or premium offerings, especially since demand appears strong.               
- Inventory Management: With the 19.73% growth in cars sold, reviewing inventory and supply chain strategies may ensure the company can sustain this demand without shortages or delays.

  ## Impact on Business
  -  Revenue Growth: The significant YOY sales growth positively impacts overall revenue and could strengthen the company’s market share in the industry.     
  -  Market Position: The increase in units sold implies the brand is resonating well with consumers, which could enhance customer loyalty and brand reputation.    
  -  Profit Margins: Slightly lower average prices may slightly impact margins, depending on cost structure, but higher sales volumes could offset this.        

   ## Recommendations    
  -  Enhance Sales Channels: Invest in expanding high-performing sales channels or exploring new marketing initiatives to sustain the YOY growth trend.    
  -  Optimize Pricing: Consider targeted price increases in areas or segments where demand is strongest or where customers are less price-sensitive.      
  -  Focus on Premium Offerings: Explore adding premium car models or feature-rich versions to elevate the average price and capture more value per sale.     
  -  Strengthen Inventory Planning: Monitor inventory closely to ensure the supply meets rising demand without risk of overstock or shortages.      


  

  

  
  





  









 
 






  
  
   



  

    

   
    
 
 





  
  
  
  
  
 

  

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
