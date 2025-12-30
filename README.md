Hotel Revenue Data Analysis (SQL)
Project Overview
This project focuses on building a unified database for hotel revenue analysis. By combining historical data from 2018 to 2020, the goal is to create a clean dataset that can be used to analyze booking trends, market segment performance, and meal costs.

Dataset Description
The data is spread across multiple tables, requiring SQL to merge and join them for a comprehensive view:

Yearly Tables: 2018$, 2019$, and 2020$ containing booking details.

Market Segment: Contains discount data for various booking types.

Meal Cost: Contains the unit cost of meals offered by the hotels.

SQL Logic Explained
The script uses two main SQL techniques:

CTEs & Unions: To consolidate three separate years of data into a single temporary result set called hotels.

Left Joins: To enrich the booking data with market segment details and meal costs without losing any original booking records.

The Query
SQL

with hotels as(
Select * from dbo.['2018$']
union
Select * from dbo.['2019$']
union
Select * from dbo.['2020$']
) 
Select * from hotels
left join dbo.market_segment$
on hotels.market_segment = market_segment$.market_segment
left join dbo.meal_cost$
on dbo.meal_cost$.meal = hotels.meal
How to Use This Project
Database Setup: Import the Excel/CSV files for the years 2018, 2019, and 2020 into your SQL Server.

Run the Script: Execute the provided .sql file to generate the unified view.

Visualization: (Optional) Connect this query to Power BI or Tableau to calculate key metrics like ADR (Average Daily Rate) and Total Revenue.

Author
Your Name - www.linkedin.com/in/adikesavareddy-katterapalli
