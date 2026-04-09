# customer-behavior-analysis
Data analytics project showcasing customer behavior analysis using python,sql and power BI.
Data Analytics Portfolio Project: Customer Shopping Behavior
Overview

This project demonstrates a complete data analytics pipeline built to reflect real-world business analysis. The goal is to analyze customer shopping behavior, identify patterns in purchasing habits, and present actionable insights through visual dashboards.

The workflow covers data collection, cleaning, exploration, SQL querying, and dashboard development, simulating the tasks performed by professional data analysts.

Project Objectives
Understand customer purchasing behavior
Identify high-value customer segments
Analyze product category trends
Build an interactive dashboard for business decision-making
Dataset

The dataset contains customer shopping activity with attributes such as:

Customer ID
Age
Gender
Location
Product Category
Purchase Amount
Payment Method
Purchase Frequency

Format: CSV

Tools & Technologies
Tool	Usage
Python	Data cleaning and analysis
Pandas	Data manipulation
NumPy	Numerical processing
Matplotlib / Seaborn	Data visualization
SQL (PostgreSQL / MySQL)	Data querying
Power BI	Dashboard visualization
Jupyter Notebook	Data analysis environment
Project Workflow
1. Data Loading

Load the dataset into Python and inspect the structure.

import pandas as pd

df = pd.read_csv("shopping_behavior.csv")

df.head()
df.info()
2. Data Cleaning

Cleaning ensures the dataset is accurate and usable.

Tasks performed:

Handling missing values
Removing duplicates
Correcting data types
Standardizing column names
df.drop_duplicates(inplace=True)

df.fillna(method="ffill", inplace=True)

df.columns = df.columns.str.lower()
3. Exploratory Data Analysis (EDA)

EDA helps uncover hidden trends in the dataset.

Customer Age Distribution
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df['age'], bins=20)
plt.title("Customer Age Distribution")
plt.show()
Gender Distribution
sns.countplot(x='gender', data=df)
plt.title("Customer Gender Distribution")
plt.show()
Product Category Popularity
df['product_category'].value_counts().plot(kind='bar')
plt.title("Product Category Sales")
plt.show()
SQL Analysis

After cleaning the data, it was loaded into a SQL database for deeper analysis.

Top Spending Customers
SELECT customer_id, SUM(purchase_amount) AS total_spent
FROM shopping_data
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;
Most Popular Product Categories
SELECT product_category, COUNT(*) AS total_sales
FROM shopping_data
GROUP BY product_category
ORDER BY total_sales DESC;
Average Purchase by Gender
SELECT gender, AVG(purchase_amount) AS avg_purchase
FROM shopping_data
GROUP BY gender;
Power BI Dashboard

An interactive dashboard was built to visualize the analysis.

Dashboard Features
Total Revenue KPI
Sales by Product Category
Customer Demographics
Purchase Trends Over Time
Payment Method Distribution
Visualizations Used
Bar Charts
Pie Charts
Line Charts
KPI Cards
Filters and Slicers
Key Insights
Certain product categories generate significantly higher sales.
Younger customers show more frequent purchasing patterns.
Payment method preferences vary by customer demographics.
Seasonal trends affect purchase volume.

These insights can support marketing strategy, product targeting, and inventory planning.

Business Recommendations

Based on the analysis:

Focus marketing on high-spending customer segments
Promote top-selling product categories
Optimize inventory during peak purchase seasons
Offer personalized discounts to increase customer retention
Project Structure
data-analytics-project

data
 └ shopping_behavior.csv

notebooks
 └ analysis.ipynb

sql
 └ analysis_queries.sql

dashboard
 └ powerbi_dashboard.pbix

README.md
How to Run the Project
Clone Repository
git clone https://github.com/yourusername/customer-shopping-analysis.git
Install Required Libraries
pip install pandas numpy matplotlib seaborn
Run Notebook
jupyter notebook

Open analysis.ipynb and run all cells.

Conclusion

This project demonstrates how raw data can be transformed into business insights using Python, SQL, and Power BI. The workflow mirrors the typical responsibilities of a data analyst and highlights skills relevant for analytics roles.
