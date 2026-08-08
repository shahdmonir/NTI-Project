📦 Supply Chain & Delivery Risk Analysis

A supply chain data analysis project built to answer one core question:

How much of our sales revenue is at risk due to late deliveries — and where exactly is it happening?

👥 Team

-Enas Nagy

-Ashraf ElSayed

-Shahd Monir

-Mariam Waleed

🧭 Project Workflow (Overview)

The project was built in this order:

Data Cleaning

 1-Data Modeling (Star Schema)

 2-Core KPI Calculation

 3-Detailed Analysis via Pivot Tables

 4-Consolidating everything into one interactive Dashboard

Each step is explained in detail below.

🧹 1) Data Cleaning & Modeling

Before any analysis, the raw data went through the following cleaning steps:

Removed duplicate, unnecessary, and sensitive personal columns (e.g. detailed customer PII not needed for analysis).
Fixed incorrect data types (e.g. numbers stored as text, dates stored as text instead of Date format).
Handled missing values so they wouldn't break downstream calculations.
Restructured the entire dataset into a Star Schema instead of one large, unorganized table.

The goal of all this: make sure every calculation and every Pivot Table built afterward is accurate and fast, with no duplication or data contamination.

🗂️ 2) Data Model (Star Schema)

The data was modeled in Power Pivot as a Star Schema: one central Fact table, connected to 5 Dimension tables around it. This structure makes filtering and analysis from multiple angles fast and flexible.

🟢 Fact_Orders (the central Fact table)

Contains the details of every order — product, customer, order date, shipping date, quantity, price, discount, profit — and most importantly:

Column	 Meaning

delay_days -> 	Number of days the delivery was delayed

delivery_status	-> Status: Delayed / Early / On Time

late_delivery_risk ->	Flag indicating whether the order was late

Total Sales	Calculated -> measure — total sales revenue

Sales at Risk	Calculated -> measure — sales value tied to late-delivered orders

Late Delivery Rate	 -> Calculated measure — percentage of late deliveries

🔵 Connected Dimension Tables : Table	Describes
Dim_Product	 -> Product details (product name, category, department)

Dim_Location	-> Location details (country, city, state, and Market — e.g. Africa / Europe / LATAM / Pacific Asia)

Dim_Shipping_Payment	-> Shipping mode, payment type, delivery status, order status

Dim_Date -> 	Order date broken down into Year / Month / Quarter

Dim_Customer ->	Customer segment and customer country

Every Dimension table is connected to Fact_Orders through a One-to-Many relationship, which is what allows any filter (e.g. filtering by a specific country or month) to instantly apply across the whole fact table.

📊 3) Core KPIs

*These are the 5 headline numbers that summarize the entire project:

KPI	Value	What it means

   -Total Sales	$36.78M	Total revenue across all orders

   -Sales at Risk	$20.13M (≈55%)	Sales value tied to orders delivered late

   -Late Delivery Rate	54.83%	Percentage of orders delivered late

   -Profit Margin	10.8%	Average profit margin

   -Avg Delay Days	~2 days	Average delay for late orders

💡 In plain terms: out of every $100 in sales, about $55 is tied to an order that arrived late — a significant and risky number for any business.

🔎 4) Pivot Tables (Detailed Analysis)

Each Pivot Table below was built to answer a specific question:

📌 Pivot 1: Late Delivery Rate by Shipping Mode

Shows each Shipping Mode (First Class, Same Day, Second Class, Standard Class) alongside its late delivery rate.

  - Shipping Mode	Late Delivery Rate
  - First Class	95%
  - Second Class	77%
  - Same Day	46%
  - Standard Class	38%

Finding: the fastest shipping mode (First Class) has the worst on-time performance! This suggests the delivery promise made to customers for First Class is unrealistic relative to actual fulfillment capacity.

📌 Pivot 2: Delay Days & Sales at Risk by Market

Aggregates, for each Market (Europe, LATAM, Pacific Asia, Africa...), the total delay days and the sales value at risk.

Finding: Europe and LATAM have the highest total delay days and the highest sales at risk, while Africa has the lowest on both fronts — a clear positive correlation between delay volume and revenue exposure.

📌 Pivot 3: Monthly Sales Trend

Shows, for each month of the year, total sales and how much of it was "at risk."

Finding: sales remain fairly stable throughout the year (~$3M/month) with a slight dip in November and December, and sales at risk consistently tracks between 45% and 55% of monthly sales — meaning this isn't a seasonal issue, it's a persistent one.

📌 Pivot 4: Delivery Status Distribution

Breaks down all 152,705 orders by delivery status:

   -Status	Count	Percentage
   -Delayed	75,586	50%
   -Early	43,366	28%
   -On Time	33,753	22%

Finding: exactly half of all orders arrive delayed — more than Early and On Time combined-adjacent figures.

📌 Pivot 5: Sales at Risk by Country & Shipping Mode

The largest pivot in the project — breaks down sales at risk per country, cross-tabulated against the four shipping modes (First Class, Same Day, Second Class, Standard Class), plus a geographic map coloring countries by sales-at-risk exposure.

Filterable via interactive Slicers:

   -market (select a specific region/continent)
   -shipping_mode (select a specific shipping method)
   -Year (select a specific year: 2015–2018)

Finding: in Africa, for example, Nigeria, South Africa, and Sudan show the highest sales at risk.

📈 5) The Final Interactive Dashboard

All the Pivot Tables above were consolidated into one interactive dashboard built in Power Pivot, containing:

5 KPI cards (Total Sales, Sales at Risk, Late Delivery Rate, Avg Delay Days, Profit Margin)
Late Delivery Rate by Shipping Mode chart
Monthly Sales vs. Sales at Risk chart
Delivery Status donut chart
Regional Delay Impact chart
Interactive geographic map of sales-at-risk exposure worldwide
3 interactive Slicers: Market, Shipping Mode, Year

Anyone opening the dashboard can filter from any angle (a specific year, region, or shipping mode) and watch every metric update live.

💡 Key Insights
  1-Over half of total sales (54.7%) are at risk due to delivery delays — a significant number.
  
  2-First Class is the least reliable shipping mode, with a 95% late delivery rate, despite supposedly being the fastest.
  
  3-Europe and LATAM carry the highest delay and risk exposure, making them the top priority for improvement.
  
  4-Exactly 50% of all orders arrive delayed — this is a year-round issue, not a seasonal one.
  
  5-Sales volume and risk aren't correlated — even in months with typical sales volume, the risk percentage stayed roughly the same.

🛠️ Tools Used

-Excel Power Pivot for building the Star Schema and calculating Measures (DAX)

-Pivot Tables & PivotCharts for detailed analysis

-Slicers for interactive filtering

-PowerPoint for presenting the results and final summary

📁 Project Contents

-File	Description

-SupplyChainProject.xlsx	Main Excel workbook: data model + all Pivot Tables + dashboard

-Supply_Chain___Delivery_Risk_Presentation.pptx	Presentation summarizing the project and findings
README.md	This file — full project explanation


✅ Summary

This project demonstrates how to take raw supply chain order data, clean it, structure it into a well-organized model (Star Schema), calculate clear performance indicators, and analyze it through Pivot Tables to reach a complete picture: where the risk is, why it's happening, and what to prioritize when fixing it.














