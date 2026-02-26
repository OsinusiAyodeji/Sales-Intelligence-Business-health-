# Sales Intelligence & Systems Engineering: Performance Diagnostic System

## Abstract Summary
This project involved building a robust Business Intelligence system to move beyond basic sales reporting. By processing over 20,590 units sold and managing a total revenue of $435.04K, I developed a **Business Health Score** to rank performance based on efficiency and sustainability rather than just volume.

![Sales Intelligence & Business Health Dashboard](Capstone%20Image.png)

## Introduction
In many businesses, high sales figures can be misleading if the costs to fulfill those sales are too high. This project was born out of a need to see the "truth" behind the numbers. I acted as the Lead Data Analyst to transform a messy, raw dataset into a scalable diagnostic tool.

The goal was simple: create a system that tells management which products are actually healthy for the business and which ones are just "busy" without being profitable. Using advanced data modeling and custom logic, I shifted the focus from "How much did we sell?" to "How well is the business actually performing?"

## Background: Context & Relevance
Most companies have plenty of data but very little intelligence. Raw spreadsheets are hard to read and even harder to act upon. This project bridges that gap by using automation to clean data and statistical analysis to highlight what actually drives the bottom line. It provides a blueprint for any business looking to prioritize high-impact products and optimize their logistics costs.

## Problem Statement
In many businesses, success is often judged only by total sales. However, looking at sales alone can be misleading. During this project, I found that products with high sales figures sometimes had very high hidden costs, such as expensive shipping fees or low profit margins. 

Without a way to balance these factors, the business couldn't tell which products were truly helping it grow and which ones were actually costing it money. There was a clear need for a "health check" system that looks at the big picture, not just the total revenue.

## Objectives
The goal of this project was to move beyond basic lists of numbers and build a tool that helps management make better decisions. My main goals were:

* **Clean and Organize Data**: Create an automated way to take messy, raw information and turn it into a clean, usable format.
* **Create a Fairness Score**: Develop a "Business Health Score" that ranks products fairly by looking at their sales, the number of units sold, and the cost to ship them.
* **Identify Big Winners**: Use the "80/20 rule" (Pareto Analysis) to prove which small group of products or categories is responsible for the majority of the company's income.
* **Build an Easy-to-Use Tool**: Design a dashboard that allows anyone to quickly see how different regions or salespeople are performing without needing to be a data expert.

## Data Description

### Data Source
The dataset for this project was provided by **AltSchool Africa** as part of a Lead Data Analyst capstone evaluation.

### Data Collection
The data was extracted from a central "Sales and Logistics" database. It represents a raw export of transactional records, specifically designed to simulate real-world data challenges, including inconsistent formatting and "dirty" entries that required significant cleaning before analysis.

### Data Characteristics
The dataset consists of detailed shipping and sales records, containing the following key attributes:

* **Order & Customer Details**: `Order ID`, `Order Date`, `Customer ID`, `Customer Name`, `Address`, `City`, `State`, `ZIP/Postal Code`, and `Country/Region`.
* **Sales Performance**: `Product Name`, `Category`, `Unit Price`, and `Quantity`.
* **Financial Metrics**: `Revenue` generated per transaction.
* **Logistics Information**: `Shipping Fee`, `Shipper Name`, `Ship Name`, `Ship Address`, `Ship City`, `Ship State`, `Ship ZIP/Postal Code`, `Ship Country/Region`, `Payment Type`, and `Shipped Date`.
* **Personnel & Geography**: `Salesperson` responsible for the transactions and the specific `Region` (East, North, South, West).

## Methodology

To ensure the insights were accurate, I followed a structured process to clean and prepare the data. I used **Power Query** as the engine for this project so that if new data is added in the future, the system will automatically clean and update itself.

### 1. Data Cleaning & Standardization
* **Duplicate Check**: Verified that there were no repeated records that could double-count sales.
* **Fixing Mistakes**: Corrected spelling errors in location names, such as changing "Los angelas" to "Los Angeles," to ensure geographical reports were accurate.
* **Data Formatting**: Ensured numbers were treated as numbers and dates were treated as dates so the system could perform math correctly.

### 2. Handling Missing Information
* **Unknowns**: For records where specific details were missing, I labeled them as "Unknown" rather than leaving them blank.
* **The "Pending" Logic**: Some orders had an order date but no shipping date. I assigned these a far-future placeholder date (01/01/2099) so the system wouldn't crash and could be filtered as outstanding orders.

### 3. Feature Engineering (New Insights)
* **Order Status**: I built a status tracker. If an order had a real shipping date, it was marked as "Completed." If it had the placeholder date, it was marked as "Pending/Cancelled."
* **Time Intelligence**: I extracted the `Month`, `Quarter`, and `Day of the Week` from the `Order Date` to identify peak performance periods.

### 4. System Automation
Instead of just loading a static table, I set up the data as a "Connection Only" model. This means the system is built to scale; it acts as an automated engine that processes raw data and feeds it directly into the dashboard without requiring manual work every time a new sale is made.

## Analysis & Custom Logic

The core of this project was moving beyond simple totals to create a diagnostic tool. To do this, I engineered a custom **Business Health Score** to rank performance fairly.

### 1. The Business Health Score Formula
A product that sells a lot but costs too much to ship isn't "healthy" for the business. I developed the following weighted formula to balance growth, demand, and costs:

$$Business\ Health\ Score = (Revenue \times 0.60 + Quantity \times 0.25) - (Shipping\ Fee \times 0.15)$$

**Logic Defense:**
* **Revenue (60%)**: Given the highest weight because income generation is the primary driver of business growth and sustainability.
* **Quantity (25%)**: High sales volume indicates strong market demand and operational throughput.
* **Shipping Fee (-15%)**: Introduced as a penalty factor. High logistics costs can erode profitability even when revenue appears strong.

### 2. Component Breakdown (Waterfall Analysis)
I created a **Waterfall Chart** that shows exactly how each factor contributes to the final total. This visualizes the "bridge" between raw revenue and the final health of the business.

![Business Health Score Component Breakdown](Water%20fall%20chart.png)

* **Revenue Impact**: $261,021.70 (The dominant driver)
* **Quantity Impact**: $5,148.00 (The volume contribution)
* **Shipping Impact**: -$6,549.46 (The cost deduction)
* **Final Health Score**: **259,620.23**

### 3. Pareto (80/20) Analysis
I performed a Pareto Analysis to identify the "Vital Few" product categories that drive the majority of the impact.

![Pareto Chart](pareto%20chart.png)

**Key Observations:**
* **The 80/20 Finding**: My analysis revealed that **53% of product categories generate ~80% of total revenue**.
* **Primary Drivers**: The top performance is driven mainly by **Beverages, Sauces, Jams & Preserves, Dairy Products, Dried Fruit & Nuts, and Canned Meat**.
* **Strategic Action**: This allows the business to prioritize inventory and marketing efforts on high-impact categories while investigating why others contribute so little to the bottom line.

## Key Insights

* **Top Performers**: **Coffee** and **Curry Sauce** are the leaders in "Business Health," contributing **44.6K** and **40.8K** points respectively. They balance high revenue with manageable logistics costs.
* **Regional Dominance**: The **New York** market is the primary revenue driver, contributing **$67K**, followed by **Portland** and **Miami** at **$50K** each.
* **The "Vital Few" Categories**: Just **53%** of categories—led by **Beverages** and **Sauces**—are responsible for approximately **80%** of total revenue.
* **Seasonal Volatility**: There are significant peaks in **June ($55.6K)** and **December ($66.6K)**, suggesting that the business is influenced by mid-year and end-of-year seasonal demand.

## Recommendations

1.  **Protect the "Health" Leaders**: Ensure top products like **Coffee** never face stockouts.
2.  **Audit Low-Value Categories**: Investigate if categories like **Grains** or **Oil** should be discontinued or restructured due to low bottom-line contribution.
3.  **Optimize Logistics in Secondary Cities**: Analyze if shipping fees in smaller markets like **Boise** and **Denver** are eating too far into margins.
4.  **Capitalize on Seasonal Trends**: Prepare inventory 1-2 months in advance for the **June** and **December** surges to handle volume without increasing shipping penalties.

## Conclusion
This project demonstrates how raw, "dirty" data can be transformed into a sophisticated system for business diagnostics. By moving beyond traditional revenue tracking and engineering a custom **Business Health Score**, I provided a way for management to identify which products are contributing most efficiently to long-term sustainability. 

Through the use of **Power Query** for automation and **Pareto Analysis** for strategic focus, this system reduces the manual workload of reporting while increasing the accuracy of business decisions.
