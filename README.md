# Pizza-Sales-Report
This project features an interactive Pizza Sales Report dashboard built with Power BI, powered by data analysis and transformation using SQL. This project analyzes key metrics such as total revenue, top-selling pizzas, peak order times, and customer preferences to derive actionable business insights for a pizza restaurant.


## Problem Statement

A pizza restaurant collects a large amount of transactional data throughout the year but lacks a centralized, visual system to analyze performance trends, customer behavior, and product popularity. Without clear insights, making informed business decisions such as optimizing the menu, identifying peak hours, or improving sales strategies becomes challenging.

This project aims to solve that problem by transforming raw sales data into a fully interactive Power BI dashboard, using SQL for data cleaning and preparation. The final report provides a year-long view of key performance indicators (KPIs) such as total revenue, sales by category, peak order times, and top-selling items, enabling data-driven decision-making.


### SQL Queries Performed on Data
- select * from pizza_sales
- select SUM(total_price) as total_revenue from pizza_sales
- SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales
- SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales
- SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales
- SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2)) AS Avg_Pizzas_per_order FROM pizza_sales

- SELECT DATENAME(DW, order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders FROM pizza_sales GROUP BY DATENAME(DW, order_date) select DATENAME(MONTH, order_date) as Month_Name, COUNT(DISTINCT order_id) as Total_Orders from pizza_sales GROUP BY DATENAME(MONTH, order_date)

- SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
FROM pizza_sales
GROUP BY pizza_category

- SELECT Top 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC

- SELECT Top 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue ASC





# Snapshot of Dashboard (Power BI Service)

![Image](https://github.com/user-attachments/assets/782d2b92-1f62-4ca3-9d5b-02755b9ac7bb)

 
 # Report Snapshot (Power BI DESKTOP)

 
![Image](https://github.com/user-attachments/assets/ed494883-fde1-4bbb-85e1-c819ace40eae)
![Image](https://github.com/user-attachments/assets/ff0ed905-a18a-4a6e-9462-4d7d5001cbd3)

# Kpi's Requirement

We need to analyze key indicators for our pizza sales data to gain insights into our business performance. Specifically, we want to calculate the following metrics:

1. Total Revenue: The sum of the total price of all pizza orders.

2. Average Order Value: The average amount spent per order, calculated by dividing the total revenue by the total number of orders.

3. Total Pizzas Sold: The sum of the quantities of all pizzas sold.

4. Total Orders: The total number of orders placed.

5. Average Pizzas Per Order: The average number of pizzas sold per order, calculated by dividing the total number of pizzas sold by the total number of orders.

# Problem Statement
## Charts Requirement

We would like to visualize various aspects of our pizza sales data to gain insights and understand key trends. We have identified the following requirements for creating charts:

1.Daily Trend for Total Orders:

Create a bar chart that displays the daily trend of total orders over a specific time period. This chart will help us identify any patterns or fluctuations in order volumes on a daily basis.

2.Monthly Trend for Total Orders:

Create a line chart that illustrates the hourly trend of total orders throughout the day. This chart will allow us to identify peak hours or periods of high order activity.

3.Percentage of Sales by Pizza Category:

Create a pie chart that shows the distribution of sales across different pizza categories. This chart will provide insights into the popularity of various pizza categories and their contribution to overall sales.

4. Percentage of Sales by Pizza Size:

Generate a pie chart that represents the percentage of sales attributed to different pizza sizes. This chart will help us understand customer preferences for pizza sizes and their impact on sales.

5.Total Pizzas Sold by Pizza Category:

Create a funnel chart that presents the total number of pizzas sold for each pizza category. This chart will allow us to compare the sales performance of different pizza categories.

6.Top 5 Best Sellers by Revenue, Total Quantity and Total Orders

Create a bar chart highlighting the top 5 best-selling pizzas based on the Revenue, Total Quantity, Total Orders. This chart will help us identify the most popular pizza options.

7. Bottom 5 Best Sellers by Revenue, Total Quantity and Total Orders

Create a bar chart showcasing the bottom 5 worst-selling pizzas based on the Revenue, Total Quantity,Total Orders.This chart will enable us to identify underperforming or less popular pizza options.
