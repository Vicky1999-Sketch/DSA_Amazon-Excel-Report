# Amazon Product Review Analysis Report
*Disclaimer: The dataset used in this analysis is for educational and analytical purposes only.*

![Amazon Dashboard](https://github.com/user-attachments/assets/bdd418c5-c778-46b7-85fc-7d01e3bc843c)

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

   * Product Type:
     ```excel
     =IF(H323=0,C323,H323)
     ```
   * Review Count:
     ```excel
     =COUNTA(O323:V323)
     ```
   * Potential Revenue (Actual Price × Rating Count):
     ```excel
     =[@[actual_price]]*[@[rating_count]]
     ```
   * Price Range Buckets:
     ```excel
     =IF([@[actual_price]]<200, "<200", IF([@[actual_price]]<=500, "200-500",IF([@[actual_price]]>500,">500","Nil")))
     ```
   * Combined Score (Rating × Review Count):
     ```excel
     =[@rating]*[@[Review count]]
     ```
   * Rating Distribution Groupings:
     ```excel
     =IF([@rating]<2,"0-1.9",IF([@rating]<3,"2.0-2.9",IF([@rating]<4,"3.0-3.9",IF([@rating]<5,"4.0-4.9",IF([@rating]>=5,"5.0 and above","None")))))
     ```

## VIII. Findings & Insights

### 1. Average Discount Percentage by Product Category

![ADC by P](https://github.com/user-attachments/assets/0e5ba900-3053-4aac-b0ba-9133985f1d25)

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

**Finding/Insight:**
Home Improvement products enjoy the highest average discount. In contrast, Toys & Games receive no discounts.

### 2. Number of Products per Category

![NP under C](https://github.com/user-attachments/assets/92e840c6-14f4-4972-9bd4-0436261c8370)

**Findings:**
* Electronics – 511
* Home & Kitchen – 448
* Computer & Accessory – 392
* Office Products – 31
* Others – Very few (1–2 items each)

**Insight:**
The Electronics category has the largest product count.

### 3. Total Number of Reviews by Category

![NR per C](https://github.com/user-attachments/assets/5d96ec21-5d58-4b36-99fb-32abdc879335)

**Findings:**
* Electronics – 3,975
* Home & Kitchen – 3,513
* Computer & Accessory – 3,111

**Insight:**
These three categories dominate in customer engagement.

## 4. Highest Average Ratings

#![P with HAR](https://github.com/user-attachments/assets/4acb80c6-3406-46e5-be5b-192ac76a46a2)

**Finding:**
Tablet products have the highest average rating of **4.6**.

### 5. Average Actual vs. Discounted Price by Category

![AAP vs DP](https://github.com/user-attachments/assets/ea011963-8547-43c3-8b08-ea64bce59580)

**Visualization:** Scatter Plot
(*Insert visual*)
**Insight:**
Varies widely by category, but steep discounts are often seen on higher-priced products.

### 6. Products with the Highest Number of Reviews

![PHN of R](https://github.com/user-attachments/assets/7dd00bff-df59-4882-a0a9-d166248289b3)

**Finding:**
USB Cables: 1,407 reviews (highest)

### 7. Products with Discounts ≥ 50%

```excel
=COUNTIF(Amazon_table[discount_percentage],">=50%")
```

**Finding:**
695 out of 1,389 products
**Insight:**
About 50% of products are heavily discounted.

*Insight:**
Most products have favorable ratings (4.0–4.9), indicating customer satisfaction.

### 8. Distribution of Product Ratings

![DPR](https://github.com/user-attachments/assets/3e1bd3fa-eecf-4747-b4c9-6d14d6aed564)

**Findings:**

* 4.0–4.9 stars: 1,039 products
* 3.0–3.9 stars: 340 products
* 2.0–2.9 stars: 6 products
* <2.0 stars: 1 product
* 5.0 stars: 3 products

**Insight:**
Most products have favorable ratings (4.0–4.9), indicating customer satisfaction.

### 9. Total Potential Revenue by Category

![TPR by C](https://github.com/user-attachments/assets/74fb9e36-c795-42de-a398-caebb206a5c1)

**Findings (in millions):**

* Electronics – ₹96,937M
* Computer & Accessory – ₹12,015M
* Home & Kitchen – ₹10,460M
  (Others < ₹200M each)

**Insight:**
Electronics have both high volume and revenue potential.

### 10. Unique Products per Price Range

![N of UP per PR](https://github.com/user-attachments/assets/698ac8af-176d-4357-a34b-2d77af858527)


**Findings:**

* ₹500 – 1,199 products
* ₹200–₹500 – 155 products
* ₹200 – 35 products

**Insight:**
Most products fall into the premium price segment.

### 11. Rating vs. Discount Relationship

![RRDL](https://github.com/user-attachments/assets/d233a698-fae6-466c-a785-17366b66d62c)


**Findings:**
Products rated 4.0–4.9 also tend to have higher discount rates.

**Insight:**
Well-rated products may be discounted to drive volume further.

### 12. Products with Fewer than 1,000 Reviews

```excel
=SUMIF(Amazon_table[Product type],A3,Amazon_table[Review count])
=COUNTIF(B:B,"<1000")
```
**Finding:**
194 of 195 product types have <1,000 reviews. Only USB cables exceed this.

### 13. Categories with the Highest Discounts

**Finding:**
Based on average discount percentage score, categories that have products with the highest discounts are Home Improvevement by 58%, followed by Home and Accessories and Home and Personal Care by 54% and 53% respectively

### 14. Top 5 Products by Rating × Review Count

![Top 5 P  RNR](https://github.com/user-attachments/assets/f7fe9874-8789-40ec-a718-40ce4f3cf3f2)
**Findings (Combined Score):**

1. USB Cables (B08Y1TFSP6): 93.6
2. USB Cables (B00NH11KIK): 72
3. Micro SD (B0BDRVFDKP): 70.4
4. HDMI Cables (B07KSMBL2H): 70.4
5. USB Cables (B01GGKYKQM): 68.8

**Insight:**
The top performers are mainly from the Computer & Accessory and Electronics categories.

## IX. Recommendations
1. Discounting works as a strategy but selectively. The data shows that categories with high discounts (e.g., Computer & Accessory, Electronics) are also leaders in review volume and revenue. However, categories like Home & Kitchen perform well despite lower discounts, suggesting strong product utility or brand value. One key recommendation would be to maintain strategic discounts on Electronics and Computer & Accessory items to sustain volume and visibility while providing bundle offerings in Home & Kitchen products to increase sales without relying solely on discounting.
2. Re-evaluate discounts in low-performing categories (e.g., Office Products, Toys) — the return on discount may not justify the cost.
3. Increase promotion of high-rated products with fewer reviews to boost engagement.
5. Monitor margins for heavily discounted products to avoid losses, even with high sales.

## X. Conclusion

The analysis highlights the impact of product category, discounting, and customer feedback on potential revenue and customer engagement. Strategic discounting is effective when paired with high-performing categories, but may not yield results across all product types.

## Dashboard

![Amazon Dashboard](https://github.com/user-attachments/assets/bdd418c5-c778-46b7-85fc-7d01e3bc843c)









