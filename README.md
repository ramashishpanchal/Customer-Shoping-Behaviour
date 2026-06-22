# Customer Shopping Behavior Analysis

## 📌 Project Overview

This project analyzes customer shopping behavior using transactional data from **3,900 purchases** across various product categories. The goal is to uncover insights into spending patterns, customer segments, product preferences, and subscription behavior to guide strategic business decisions.

The analysis pipeline spans three stages:
1. **Python** — data cleaning, preparation, and feature engineering
2. **SQL (MySQL)** — structured business analysis
3. **Power BI** — interactive dashboard for visual storytelling

---

## 📊 Dataset Summary

| Attribute | Details |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `Review Rating` column |

**Key Features:**
- **Customer demographics:** Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount, Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

---

## 🐍 Exploratory Data Analysis (Python)

Data preparation and cleaning steps performed:

- **Data Loading:** Imported the dataset using `pandas`.
- **Initial Exploration:** Used `df.info()` to check structure and `.describe()` for summary statistics.
- **Missing Data Handling:** Checked for null values and imputed missing values in the `Review Rating` column using the median rating of each product category.
- **Column Standardization:** Renamed columns to snake_case for better readability and documentation.
- **Feature Engineering:**
  - Created `age_group` column by binning customer ages.
  - Created `purchase_frequency_days` column from purchase data.
- **Data Consistency Check:** Verified that `discount_applied` and `promo_code_used` were redundant; dropped `promo_code_used`.
- **Database Integration:** Connected the Python script to MySQL and loaded the cleaned DataFrame into the database for SQL analysis.

### Summary Statistics

| Metric | Customer ID | Age | Purchase Amount (USD) | Review Rating | Previous Purchases |
|---|---|---|---|---|---|
| count | 3900 | 3900 | 3900 | 3863 | 3900 |
| mean | 1950.5 | 44.07 | 59.76 | 3.75 | 25.35 |
| std | 1125.98 | 15.21 | 23.69 | 0.72 | 14.45 |
| min | 1 | 18 | 20 | 2.5 | 1 |
| 25% | 975.75 | 31 | 39 | 3.1 | 13 |
| 50% | 1950.5 | 44 | 60 | 3.8 | 25 |
| 75% | 2925.25 | 57 | 81 | 4.4 | 38 |
| max | 3900 | 70 | 100 | 5.0 | 50 |

---

## 🗄️ Data Analysis (SQL — PostgreSQL)

Structured analysis was performed in PostgreSQL to answer key business questions:

1. **Revenue by Gender** — Male customers generated significantly higher total revenue (₹157,890) than female customers (₹75,191).
2. **High-Spending Discount Users** — Identified 839 customers who used discounts but still spent above the average purchase amount.
3. **Top 5 Products by Rating** — Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78).
4. **Shipping Type Comparison** — Express shipping had a slightly higher average purchase amount (₹60.48) than Standard (₹58.46).
5. **Subscribers vs. Non-Subscribers** — Non-subscribers (2,847 customers) generated far more total revenue (₹170,436) than subscribers (1,053 customers, ₹62,645), though average spend was similar (~₹59.5–59.9).
6. **Discount-Dependent Products** — Hat (50.0%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%) had the highest share of discounted purchases.
7. **Customer Segmentation** — Customers classified into Loyal (3,116), Returning (701), and New (83) segments.
8. **Top 3 Products per Category:**
   - Accessories: Jewelry, Sunglasses, Belt
   - Clothing: Blouse, Pants, Shirt
   - Footwear: Sandals, Shoes, Sneakers
   - Outerwear: Jacket, Coat
9. **Repeat Buyers & Subscriptions** — Of 2,518 non-subscribed customers and 958 subscribed customers, repeat buying (>5 purchases) did not clearly correlate with higher subscription rates.
10. **Revenue by Age Group** — Young Adult (₹62,143) > Middle-aged (₹59,197) > Adult (₹55,978) > Senior (₹55,763).

---

## 📈 Dashboard (Power BI)

An interactive **Customer Behavior Dashboard** was built in Power BI featuring:

- **KPI Cards:** 3.9K customers, ₹59.76 average purchase amount, 3.75 average review rating
- **Filters/Slicers:** Subscription Status, Gender, Category, Shipping Type
- **Visuals:**
  - % of customers by subscription status (donut chart)
  - Revenue by category
  - Sales by category
  - Revenue by age group
  - Sales by age group

---

## 💡 Business Recommendations

- **Boost Subscriptions** — Promote exclusive benefits for subscribers.
- **Customer Loyalty Programs** — Reward repeat buyers to move them into the "Loyal" segment.
- **Review Discount Policy** — Balance sales boosts with margin control.
- **Product Positioning** — Highlight top-rated and best-selling products in campaigns.
- **Targeted Marketing** — Focus efforts on high-revenue age groups and express-shipping users.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python (pandas) | Data cleaning, feature engineering |
| MySQL | Data storage / integration layer |
| MySQL | Business query analysis |
| Power BI | Dashboard & data visualization |

---

## 📁 Project Structure (Suggested)

```
customer-shopping-behavior-analysis/
│
├── customer_shopping_behaviour.csv
│
├── customer_shoping_behaviour.ipynb
│
├── Customer shoping behaviour sql queries.sql
│
├── customer_behavior_dashboard.pbix
│
└── README.md
```

---

## 📬 Contact

For questions or collaboration on this project, feel free to reach out.
