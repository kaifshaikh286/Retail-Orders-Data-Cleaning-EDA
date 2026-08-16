# 🛒 Messy Retail Orders — Data Cleaning & Exploratory Data Analysis

## 📌 Project Overview
This project takes a real-world-style **messy e-commerce/retail dataset** (420 rows, 10 columns) and transforms it into a clean, analysis-ready dataset using **Python and pandas**. The cleaned data is then explored to uncover business insights around product performance, city-wise revenue, payment behavior, and monthly sales trends.

## 🎯 Problem Statement
The raw dataset contained several common real-world data quality issues:
- **18 duplicate rows**
- **Missing values** across every column (Age, City, ProductCategory, Price, Quantity, PaymentMode, OrderDate, Rating)
- **Inconsistent text formatting** — mixed casing (`bengaluru` vs `MUMBAI`), extra whitespace (`" Chennai"`)
- **Inconsistent category labels** — e.g., `"COD"` and `"Cash On Delivery"` referring to the same payment method
- **4 different date formats** mixed within a single `OrderDate` column (`DD/MM/YYYY`, `YYYY-MM-DD`, `DD-MM-YYYY`, `MM/DD/YYYY`)

## 🛠️ Tools Used
- Python
- pandas
- matplotlib
- Jupyter Notebook

## 🧹 Data Cleaning Steps
1. **Removed 18 duplicate rows** using `drop_duplicates()`
2. **Handled missing values**:
   - Numeric columns (Age, Price, Quantity, Rating) → filled with **median**
   - Categorical columns (City, ProductCategory, PaymentMode) → filled with **'Unknown'**
   - Rows with missing `OrderDate` → dropped (a transaction date cannot be logically inferred)
3. **Standardized text columns** — stripped whitespace and applied consistent casing (Title Case for names/cities, UPPERCASE for payment codes)
4. **Merged inconsistent category labels** (e.g., `"CASH ON DELIVERY"` → `"COD"`)
5. **Parsed mixed date formats** into a single standardized `datetime` type using `pd.to_datetime(..., dayfirst=True, format='mixed', errors='coerce')`

**Result:** 420 rows → **390 clean, analysis-ready rows**, zero missing values, zero duplicates.

## 📊 Exploratory Data Analysis — Key Insights
1. **Electronics** is the top-performing category both by order count (102) **and** total revenue (₹43.1L), followed closely by Clothing.
2. **Chennai, Mumbai, and Hyderabad** together drive the majority of revenue; **Pune** significantly underperforms (₹4.8L vs Chennai's ₹25.2L).
3. **Bengaluru had more orders than Hyderabad**, but **Hyderabad generated more revenue** — showing order count and revenue don't always align.
4. **UPI** is both the most-used payment method (105 orders) **and** among the highest in average order value (₹40,873) — a strong-performing channel.
5. **April showed a significant revenue dip** (₹7.19L) compared to all other months (₹11.5L–₹14.2L average), worth further business investigation.

## 📈 Visualizations
![Revenue by Product Category](revenue_by_category.png)
![Revenue by City](revenue_by_city.png)

## 📁 Files in this Repository
- `messy_retail_orders.csv` — original raw dataset
- `cleaned_retail_orders.csv` — cleaned, analysis-ready dataset
- `retail_orders_analysis.ipynb` — full Jupyter notebook (cleaning + EDA + visualizations)
- `README.md` — this file

## 🚀 Key Takeaways
This project demonstrates practical data cleaning skills including handling missing values with context-appropriate strategies, resolving inconsistent categorical labels, parsing mixed date formats, and deriving actionable business insights through exploratory data analysis.

---
**Author:** Kaif Shaikh | [GitHub](https://github.com/kaifshaikh286)
