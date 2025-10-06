Retail Sales Analysis Using SQL (PostgreSQL)
Project Overview

This project explores retail transaction data using PostgreSQL, focusing on uncovering business insights such as customer purchasing behavior, category performance, and sales trends over time.
It was completed as a self-learning project by following Najir Hossain’s Retail Sales SQL tutorial
 and using the dataset provided in his GitHub repository
.
Through this project, I practiced database design, data cleaning, exploratory SQL queries, and business analysis using SQL window functions and aggregations.

Tools & Technologies

Database: PostgreSQL

Environment: pgAdmin / SQL Shell (psql)

Language: SQL

Dataset: SQL - Retail Sales Analysis_utf.csv

Reference Tutorial: Najir Hossain’s GitHub – Retail Sales Analysis Project (P1)

Database Schema

A single table named retail_sales was created to store all transactional data:

Column	Description
transactions_id	Unique transaction ID (Primary Key)
sale_date	Date of sale
sale_time	Time of sale
customer_id	Unique customer identifier
gender	Customer gender
age	Customer age
category	Product category (e.g., Clothing, Electronics, Beauty)
quantity	Quantity purchased
price_per_unit	Price per item
cogs	Cost of goods sold
total_sale	Total sale value for the transaction
Data Cleaning

Before analysis, null and missing values were removed to ensure data consistency:

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


This step ensured that all queries and aggregations were based on complete, valid records.

Exploratory Queries

Basic exploration was performed to understand data volume, diversity, and structure:

Total number of sales

Number of unique customers

Product categories available

Data validation for missing values and duplicates

Business Questions Answered

The project used SQL queries to address ten business-focused analytical questions:

Retrieve all sales made on November 5, 2022.

Find transactions where category = ‘Clothing’ and quantity > 4 in November 2022.

Calculate total sales and number of orders by category.

Find the average age of customers who purchased from the Beauty category.

Identify all high-value transactions (total sale > 1000).

Count total transactions by gender and category.

Calculate the average sale per month and determine the best-selling month per year.

Find the Top 5 customers based on total sales value.

Count the number of unique customers per category.

Categorize transactions by time of day (Morning, Afternoon, Evening) based on sale_time.

Key Insights

Clothing and Beauty emerged as the top-performing categories.

The Afternoon shift recorded the highest sales volume, suggesting peak shopping hours.

The average age of customers purchasing Beauty products was younger than other categories.

A small group of loyal customers contributed significantly to total revenue.

How to Reproduce

Clone this repository or download the SQL and CSV files.

Open your PostgreSQL environment (e.g., pgAdmin).

Create a new database and execute the SQL script:

\i retail_sales_analysis.sql


Import the dataset SQL - Retail Sales Analysis_utf.csv into the retail_sales table.

Run each query block to reproduce the analysis and explore insights.

Future Enhancements

Build a dashboard in Tableau or Power BI for interactive visualization.

Integrate multiple years of data for trend analysis.

Create stored procedures and triggers to automate summary reports.

Credits

Tutorial Author: Najir Hossain

YouTube Guide: Retail Sales Analysis SQL Project (P1)

Dataset Source: Author’s GitHub Repository

Project Practice & Documentation: Vi Truong
