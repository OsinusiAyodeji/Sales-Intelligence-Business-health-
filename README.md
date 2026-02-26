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

* **Order & Customer Details**: Unique Order IDs, Customer Names, and full contact/location details (City, State, Country).
* **Sales Performance**: Product Names, Categories, Unit Prices, and Quantities sold.
* **Financial Metrics**: Total Revenue generated per transaction.
* **Logistics Information**: Shipping Fees, Shipper Names, and specific shipment dates (Order Date vs. Shipped Date).
* **Personnel & Geography**: Salespeople responsible for the transactions and the specific Regions (East, North, South, West) where the sales occurred.

## Methodology

To ensure the insights were accurate, I followed a structured process to clean and prepare the data. I used **Power Query** as the engine for this project so that if new data is added in the future, the system will automatically clean and update itself.

### 1. Data Cleaning & Standardization
Raw data is rarely perfect. I performed several steps to ensure the information was consistent:
* **Duplicate Check**: Verified that there were no repeated records that could double-count sales.
* **Fixing Mistakes**: Corrected spelling errors in location names, such as changing "Los angelas" to the correct "Los Angeles," to ensure geographical reports were accurate.
* **Data Formatting**: Ensured numbers were treated as numbers and dates were treated as dates so the system could perform math correctly.

### 2. Handling Missing Information
Not every record was complete, so I applied logic to fill the gaps:
* **Unknowns**: For records where specific details were missing, I labeled them as "Unknown" rather than leaving them blank.
* **The "Pending" Logic**: Some orders had an order date but no shipping date. I assigned these a far-future placeholder date (01/01/2099) so the system wouldn't crash.

### 3. Feature Engineering (New Insights)
I created new columns to help management see patterns that weren't visible in the raw data:
* **Order Status**: I built a status tracker. If an order had a real shipping date, it was marked as "Completed." If it had the placeholder date, it was marked as "Pending/Cancelled."
* **Time Intelligence**: I broke down the order dates into Months, Quarters, and Days of the Week. This allows us to see exactly when the business is busiest.

### 4. System Automation
Instead of just loading a static table, I set up the data as a "Connection Only" model. This means the system is built to scale; it acts as an automated engine that processes raw data and feeds it directly into the dashboard without requiring manual work every time a new sale is made.





















