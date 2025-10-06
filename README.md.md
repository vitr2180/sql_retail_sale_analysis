\# Retail Sales Analysis 



\## Project Overview

This project analyzes retail transaction data to uncover key insights into customer behavior, sales performance, and product category trends using PostgreSQL.

It was completed as a self-learning exercise by following a YouTube tutorial by Najir Hossain and replicating his project using the dataset from his GitHub repository.



YouTube tutorial: https://www.youtube.com/watch?v=ChIQjGBI3AM\&t=356s

GitHub source: https://github.com/najirh/Retail-Sales-Analysis-SQL-Project--P1/tree/main



The goal of this project was to strengthen SQL querying skills by performing end-to-end data cleaning, exploration, and analysis to answer real-world business questions.



---



\## Tools and Technologies

\- Database: PostgreSQL

\- Interface: pgAdmin 4

\- Language: SQL

\- Dataset: SQL - Retail Sales Analysis\_utf.csv

\- Script File: retail\_sales\_analysis.sql



---



\## Database Design

A single table named `retail\_sales` was created to store transaction-level data.



Columns and descriptions:

\- transactions\_id (INT, Primary Key) — Unique transaction ID

\- sale\_date (DATE) — Date of sale

\- sale\_time (TIME) — Time of sale

\- customer\_id (INT) — Unique customer identifier

\- gender (VARCHAR) — Customer gender

\- age (INT) — Customer age

\- category (VARCHAR) — Product category (e.g., Clothing, Electronics, Beauty)

\- quantity (INT) — Quantity purchased

\- price\_per\_unit (FLOAT) — Price per item

\- cogs (FLOAT) — Cost of goods sold

\- total\_sale (FLOAT) — Total sale value of the transaction



---



\## Data Cleaning

Null or missing records were identified and removed to ensure high data quality.



Example query:

DELETE FROM retail\_sales

WHERE transactions\_id IS NULL

&nbsp;  OR sale\_date IS NULL

&nbsp;  OR sale\_time IS NULL

&nbsp;  OR customer\_id IS NULL

&nbsp;  OR gender IS NULL

&nbsp;  OR age IS NULL

&nbsp;  OR category IS NULL

&nbsp;  OR quantity IS NULL

&nbsp;  OR price\_per\_unit IS NULL

&nbsp;  OR cogs IS NULL

&nbsp;  OR total\_sale IS NULL;



This ensured that only complete and valid transactions remained for analysis.



---



\## Exploratory Data Analysis (EDA)

Basic data exploration was performed to understand the dataset’s structure and confirm integrity.



Example queries:

SELECT COUNT(\*) AS total\_records FROM retail\_sales;

SELECT COUNT(DISTINCT customer\_id) AS total\_customers FROM retail\_sales;

SELECT DISTINCT category FROM retail\_sales;



---



\## Business Questions and Analysis

The project answers ten key business questions:



1\. Retrieve all sales made on '2022-11-05'.

2\. Find all transactions where category = 'Clothing' and quantity > 4 in November 2022.

3\. Calculate total sales and number of orders for each category.

4\. Find the average age of customers who purchased from the 'Beauty' category.

5\. Retrieve all transactions where total\_sale > 1000.

6\. Find total transactions by gender and category.

7\. Determine the best-selling month in each year based on average monthly sales.

8\. Identify the top 5 customers based on total sales.

9\. Find the number of unique customers per category.

10\. Group transactions by shift (Morning, Afternoon, Evening) based on sale\_time.



Key SQL concepts used:

\- Aggregations: SUM, AVG, COUNT

\- Window functions: RANK() OVER(...)

\- Conditional logic: CASE WHEN

\- Date/time extraction: EXTRACT(YEAR FROM sale\_date)



---



\## Key Insights

\- Clothing and Beauty categories generated the highest total sales.

\- Afternoon hours recorded the highest transaction count.

\- Customers aged 25–40 were the most active buyers.

\- A small group of customers contributed a significant share of total revenue.

\- November showed the highest average sales, indicating strong seasonal trends.



---



\## How to Run This Project

1\. Clone the repository:

&nbsp;  git clone https://github.com/yourusername/retail-sales-sql-analysis.git

2\. Open pgAdmin and create a new PostgreSQL database.

3\. Import the dataset SQL - Retail Sales Analysis\_utf.csv into the retail\_sales table.

4\. Run the SQL script retail\_sales\_analysis.sql sequentially to create the table, clean data, and perform analysis.

5\. Modify or extend queries to explore further insights.



---



\## Future Enhancements

\- Add visual dashboards using Tableau or Power BI.

\- Create database views and stored procedures for recurring reports.

\- Integrate with Python or R for predictive modeling.

\- Expand the dataset to include multiple stores or years.



---



\## Author and Credits

\- Tutorial by: Najir Hossain

\- Dataset Source: Najir’s GitHub Repository

\- Recreated and Analyzed by: Vi Truong

\- Database Used: PostgreSQL

