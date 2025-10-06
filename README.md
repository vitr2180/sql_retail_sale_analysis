# 🛒 Retail Sales Analysis Using SQL (PostgreSQL)

## 📘 Project Overview
This project explores retail transaction data using **PostgreSQL**, focusing on uncovering business insights such as customer purchasing behavior, category performance, and sales trends over time.  
It was completed as a self-learning project by following [Najir Hossain’s Retail Sales SQL tutorial](https://www.youtube.com/watch?v=ChIQjGBI3AM&t=356s) and using the dataset provided in his [GitHub repository](https://github.com/najirh/Retail-Sales-Analysis-SQL-Project--P1/tree/main).

Through this project, I practiced:
- Database design and data cleaning  
- Exploratory SQL queries  
- Business analysis using window functions and aggregations  

---

## 🧰 Tools & Technologies
- **Database:** PostgreSQL  
- **Environment:** pgAdmin / SQL Shell (psql)  
- **Language:** SQL  
- **Dataset:** `SQL - Retail Sales Analysis_utf.csv`  
- **Reference Tutorial:** Najir Hossain’s GitHub – *Retail Sales Analysis Project (P1)*  

---

## 🧩 Database Schema
A single table named **`retail_sales`** was created to store all transactional data.

| Column | Description |
|--------|--------------|
| `transactions_id` | Unique transaction ID (Primary Key) |
| `sale_date` | Date of sale |
| `sale_time` | Time of sale |
| `customer_id` | Unique customer identifier |
| `gender` | Customer gender |
| `age` | Customer age |
| `category` | Product category (e.g., Clothing, Electronics, Beauty) |
| `quantity` | Quantity purchased |
| `price_per_unit` | Price per item |
| `cogs` | Cost of goods sold |
| `total_sale` | Total sale value for the transaction |

---

## 🧹 Data Cleaning
Before analysis, null and missing values were removed to ensure data consistency:

```sql
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

---


## 🔍 Exploratory Queries
Basic exploration was performed to understand data volume, diversity, and structure:

- **Total number of sales**
- **Number of unique customers**
- **Product categories available**
- **Data validation for missing values and duplicates**

---

## 🧠 Business Questions Answered
The project used SQL queries to answer 10 business-focused analytical questions:

1. Retrieve all sales made on **November 5, 2022**.  
2. Find transactions where the category is **'Clothing'** and **quantity > 4** in **November 2022**.  
3. Calculate **total sales** and **number of orders** by category.  
4. Find the **average age** of customers who purchased from the **Beauty** category.  
5. Identify all **high-value transactions** where **total_sale > 1000**.  
6. Count total transactions by **gender** and **category**.  
7. Calculate the **average sale per month** and find the **best-selling month per year**.  
8. Identify the **Top 5 customers** based on total sales value.  
9. Count the **number of unique customers** per category.  
10. Categorize transactions by **time of day** (Morning, Afternoon, Evening) based on `sale_time`.

---

## 📈 Key Insights
- **Clothing** and **Beauty** were the top-performing categories.  
- The **Afternoon shift** recorded the highest number of transactions.  
- The **average customer age** in the Beauty category was lower than in other segments.  
- A small group of **loyal customers** generated a significant portion of total sales.  

---

## ⚙️ How to Reproduce
1. Clone this repository or download the files.  
2. Open your PostgreSQL environment (pgAdmin or psql).  
3. Create a new database and run the SQL script:
   ```sql
   \i retail_sales_analysis.sql
