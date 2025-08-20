#Sales Inisght Project

Developed an interactive Sales Insight Dashboard to analyze and visualize company sales performance across regions, products, and customer segments. 
The project aimed to provide business leaders with data-driven insights to improve decision-making, optimize sales strategies, and identify growth opportunities.

Key Features:-

1.Collected and cleaned raw sales data using Excel / SQL / Python.
2.Built interactive dashboards in Power BI/Tableau to track KPIs such as total sales, revenue growth, profit margin, and top-performing products.
3.Designed filters for region, time period, and product category to allow dynamic exploration of data.
4.Conducted trend analysis (monthly/quarterly/yearly) to highlight sales growth patterns.
5.Implemented customer segmentation to identify high-value customers and target markets.
6.Provided actionable insights such as identifying underperforming regions and products with the highest profitability.

Technologies & Frameworks:-

(i) Data Collection & Processing:
SQL – for querying and extracting sales data from relational databases.
Excel – for initial data cleaning, pivot tables, and pre-processing.
Python (Pandas, NumPy) – for advanced data cleaning, transformation, and exploratory data analysis (EDA).

(ii) Data Visualization & Business Intelligence:
Power BI – for building interactive dashboards, KPI tracking, and DAX measures.

(iii) Frameworks / Supporting Tools:
DAX (Data Analysis Expressions) – to create calculated fields and measures in Power BI.
ETL Frameworks – basic ETL pipeline using Python/SQL for data extraction and transformation.

SOURCE:-
https://drive.google.com/file/d/1pXUPADPUsEaygBrWdBPfuKGL_FEjlVXq/view?usp=drivesdk

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`






