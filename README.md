# EDA-USING-MYSQL
# Electronics Data Analysis in MySQL

This project is a complete Exploratory Data Analysis (EDA) of an electronics dataset using only MySQL. I took raw, messy data and cleaned it up step-by-step to find real business insights and statistical trends.

## What I Did

* **Data Cleaning:** The original data had prices and discounts mixed with text and symbols. I used Regular Expressions (Regex) and string functions like `SUBSTRING_INDEX` to pull out just the clean numbers so I could do math on them.
* **Feature Engineering:** I created new, useful columns out of the old ones. I extracted exact star ratings and review counts from long sentences, calculated the final Maximum Retail Price (MRP) based on different discount rules, and pulled brand names right out of the product titles.
* **Univariate Analysis & Outliers:** MySQL doesn't have a built-in function to find percentiles, so I wrote a custom Stored Procedure to calculate them from scratch. I used those percentiles to find the Interquartile Range (IQR) and spot outlier prices, showing that the price data is positively skewed.
* **Advanced Statistics:** I wrote SQL queries to calculate Covariance, Correlation, and the Slope between product ratings and the number of reviews to see how they affect each other.

## Key Findings

* **Price Distribution:** The prices have several high-end outliers. This means most products are affordable, but a few premium items stretch the average up.
* **Ratings vs. Reviews:** The slope between ratings and reviews is 19.26. This means for every 1-point increase in a product's average rating, we generally expect to see about 19 more reviews. However, the correlation score (0.013) is very weak, showing this is just a loose trend, not a strong direct link.
* **Brand Spread:** Apple leads the pack by offering products across 7 different sub-categories, followed by Lenovo and Sony.

## Tools & Techniques Used

* **Database:** MySQL
* **Techniques:** Data Cleaning, Regular Expressions (Regex), Custom Stored Procedures, Window Functions (`PERCENT_RANK()`), Mathematical Aggregations (`STD`, `POWER`, `AVG`), and Subqueries.

## How to Run This Project

1. Download the raw `ElectronicsData.csv` file.
2. Open MySQL Workbench (or your preferred SQL editor).
3. Run the provided `.sql` script to create the database, load the data, and execute the analysis step-by-step.
