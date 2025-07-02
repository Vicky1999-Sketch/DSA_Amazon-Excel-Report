# Amazon Product Review Analysis Report
*Disclaimer: The dataset used in this analysis is for educational and analytical purposes only.*

## I. Introduction
This report provides an analysis of product and customer review data to generate insights that can guide product improvement, marketing strategies, and customer engagement.

## II. Data Description
The dataset consists of a single table containing 16 columns:
**\[Product ID, Product Name, Category, Discounted Price, Actual Price, Discount Percentage, Rating, Rating Count, About Product, User ID, User Name, Review ID, Review Title, Review Content, Image Link, Product Link]**
It includes a total of **1,465 rows**.

## III. Problem Statement
This analysis seeks to answer the following questions:
1. What is the average discount percentage by product category?
2. How many products are listed under each category?
3. What is the total number of reviews per category?
4. Which products have the highest average ratings?
5. What is the average actual price vs. discounted price by category?
6. Which products have the highest number of reviews?
7. How many products have a discount of 50% or more?
8. What is the distribution of product ratings?
9. What is the total potential revenue (actual\_price × rating\_count) by category?
10. How many unique products fall into specific price ranges?
11. What is the relationship between rating and discount level?
12. How many products have fewer than 1,000 reviews?
13. Which categories have products with the highest discounts?
14. What are the top 5 products based on rating and review count combined?

## IV. Methodology
Microsoft Excel was used for data cleaning, transformation, analysis, and visualization.

## V. Data Transformation & Cleaning
Data cleaning steps performed in Excel:
1. Verified data types and corrected any inconsistencies.
2. Removed 76 duplicate records, leaving 1,389 valid rows.
3. Dropped irrelevant columns such as *Product Name*, *About Product*, *User ID*, *Username*, *Review Title*, *Review Content*, *Image Link*, and *Product Link*.
4. Split combined fields like *Category* and *Review ID*.
5. Created calculated columns such as:

   * Product Type
   * Review Count
   * Potential Revenue (Actual Price × Rating Count)
   * Price Range Buckets
   * Combined Score (Rating × Review Count)
   * Rating Distribution Groupings

## VII. Calculations and Formulas Used

(*Section reserved for formulas such as `=AVERAGEIF()`, `=COUNTIF()`, `=IF()`, etc.*)

## VIII. Findings & Insights

### 1. Average Discount Percentage by Product Category

**Findings:**
* Home Improvement – 58%
* Computer & Accessory – 54%
* Health & Personal Care – 53%
* Electronics – 50%
* Musical Instruments – 46%
* Car & Motorbike – 42%
* Home & Kitchen – 40%
* Office Products – 12%
* Toys & Games – 0%

**Insight:**
Home Improvement products enjoy the highest average discount. In contrast, Toys & Games receive no discounts.

### 2. Number of Products per Category

**Findings:**
* Electronics – 511
* Home & Kitchen – 448
* Computer & Accessory – 392
* Office Products – 31
* Others – Very few (1–2 items each)

**Insight:**
The Electronics category has the largest product count.

### 3. Total Number of Reviews by Category

**Findings:**
* Electronics – 3,975
* Home & Kitchen – 3,513
* Computer & Accessory – 3,111

**Insight:**
These three categories dominate in customer engagement.

### 4. Highest Average Ratings

**Finding:**
Tablet products have the highest average rating of **4.6**.

### 5. Average Actual vs. Discounted Price by Category

**Visualization:** Scatter Plot
(*Insert visual*)
**Insight:**
Varies widely by category, but steep discounts are often seen on higher-priced products.

### 6. Products with the Highest Number of Reviews

**Finding:**
USB Cables: 1,407 reviews (highest)

### 7. Products with Discounts ≥ 50%

**Finding:**
695 out of 1,389 products
**Insight:**
About 50% of products are heavily discounted.

### 7. Products with Discounts ≥ 50%

**Finding:**
695 out of 1,389 products
**Insight:**
About 50% of products are heavily discounted.

*Insight:**
Most products have favorable ratings (4.0–4.9), indicating customer satisfaction.
