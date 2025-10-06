🛒 Retail Sales Analysis Using SQL (PostgreSQL)
📘 Project Overview

This project analyzes retail transaction data to uncover key insights into customer behavior, sales performance, and product category trends using PostgreSQL.
The project was completed as a self-learning exercise by following a YouTube tutorial by Najir Hossain
 and replicating his project structure using the dataset from his GitHub repository
.

The goal of this project was to strengthen SQL querying skills by performing end-to-end data cleaning, exploration, and analysis to answer real-world business questions.

🧰 Tools & Technologies

Database System: PostgreSQL

Interface Used: pgAdmin 4

Programming Language: SQL

Dataset: SQL - Retail Sales Analysis_utf.csv (from Najir Hossain’s GitHub)

Script File: retail_sales_analysis.sql

🧩 Database Design

A single table named retail_sales was created to store transaction-level data.

Column	Data Type	Description
transactions_id	INT (Primary Key)	Unique transaction ID
sale_date	DATE	Date of sale
sale_time	TIME	Time of sale
customer_id	INT	Unique customer identifier
gender	VARCHAR(15)	Customer gender
age	INT	Customer age
category	VARCHAR(15)	Product category (e.g., Clothing, Electronics, Beauty)
quantity	INT	Quantity purchased
price_per_unit	FLOAT	Price per item
cogs	FLOAT	Cost of goods sold
total_sale	FLOAT	Total sale value of the transaction
🧹 Data Cleaning

To ensure high-quality data for analysis, null or missing records were identified and removed using the following query:

DELETE FROM retail_sales
WHERE transactions_id IS NULL
   OR sale_date IS NULL
   OR sale_time IS NULL
   OR customer_id IS NULL
   OR gender IS NULL
   OR age IS NULL
   OR category IS NULL
   OR quantity IS NULL
   OR price_per_unit IS NULL
   OR cogs IS NULL
   OR total_sale IS NULL;


This step ensured all transactions contained valid and complete information.

📊 Exploratory Data Analysis

Before diving into insights, basic exploration was performed to understand the data’s structure and distribution:

SELECT COUNT(*) AS total_records FROM retail_sales;
SELECT COUNT(DISTINCT customer_id) AS total_customers FROM retail_sales;
SELECT DISTINCT category FROM retail_sales;


These queries helped confirm dataset integrity and highlight the range of categories and customers.

🧠 Business Questions & Analysis

The analysis focused on answering ten key business questions:

Retrieve all sales made on '2022-11-05'.

Find all transactions where category = 'Clothing' and quantity > 4 in November 2022.

Calculate total sales and number of orders for each category.

Find the average age of customers who purchased items from the 'Beauty' category.

Retrieve transactions where total sales exceeded 1000.

Calculate the total number of transactions by gender and category.

Determine the best-selling month of each year based on average monthly sales.

Identify the top 5 customers by total sales.

Count the number of unique customers purchasing from each category.

Group transactions by shift (Morning, Afternoon, Evening) based on sale time.

Each query was designed to practice advanced SQL operations such as:

Filtering and aggregation (WHERE, GROUP BY, HAVING)

Window functions (RANK() OVER(...))

Conditional logic (CASE WHEN)

Date and time functions (EXTRACT(YEAR FROM sale_date))

📈 Key Insights

Clothing and Beauty emerged as strong-performing categories by sales value.

Afternoon transactions had the highest sales frequency, indicating peak shopping hours.

Customers aged between 25–40 contributed the most purchases in Beauty and Electronics categories.

A small group of customers accounted for a large share of total revenue, representing high-value segments.

November recorded the highest average sales, suggesting a seasonal or promotional boost.

⚙️ How to Run This Project

Clone this repository or download the files:

git clone https://github.com/yourusername/retail-sales-sql-analysis.git


Open PostgreSQL (pgAdmin) and create a new database.

Import the dataset (SQL - Retail Sales Analysis_utf.csv) into your database table retail_sales.

Run the SQL script (retail_sales_analysis.sql) to create the table, clean data, and execute analysis queries.

Explore or modify the queries to extend your analysis.

🚀 Future Enhancements

Build interactive visual dashboards using Tableau or Power BI.

Automate KPI tracking with stored procedures and views.

Extend the project with additional time periods or multi-store datasets.

Integrate with Python or R for advanced analytics and machine learning.

🧑‍💻 Author & Credits

Tutorial by: Najir Hossain

Dataset Source: Najir’s GitHub Repository

Recreated and Analyzed by: Vi Truong

Database Used: PostgreSQL

Purpose: SQL Learning & Data Analytics Practice
