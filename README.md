# Shopping-Trends-Analysis-2021-2023

# 📌 Project Overview

This report analyzes 251.51M revenue, 99K transactions, and customer demographics from 2021–2023 to uncover shopping patterns across different malls, product categories, age groups, and payment preferences.

The insights help Retail, Mall Management, and Sales teams understand:

High-performing shopping malls

Customer spending patterns

Payment method preference

Category-wise performance

Gender-based revenue distribution

Month-over-month & year-over-year trends

<img width="1185" height="671" alt="Screenshot 2025-11-29 231019" src="https://github.com/user-attachments/assets/19c6623b-1d9d-43f9-9bfb-20341d9dfea3" />


# 📊 Key Performance Indicators (KPIs)
KPI	Value	Description
Total Revenue	251.51M	Total spending across all malls (2021–2023)
Total Transactions	99K	Number of orders completed
Avg. Basket Size	3.00 items	Average number of products per purchase
AOV (Average Order Value)	2.53K	Avg revenue per transaction
Revenue YoY	142.66M	Year-over-year revenue growth
Transaction MoM / YoY	Scrollable metrics in dashboard	Monthly & yearly change percentages
# 📍 Filters Used in the Dashboard

Gender

Age Group

Category

Payment Method

Shopping Mall

Month / Date / Year

Quarter

Weekday

These allow dynamic exploration to isolate specific customer behaviors.

# 📈 Key Insights
1. Revenue by Shopping Mall

Mall of Istanbul leads with ≈50.87M.

Kanyon follows at ≈50.55M.

Metrocity, Istanbul Cevahir, and Istinye Park also show strong footfall and spending.

Lower-performing malls include ViaPort Outlet and Forum Istanbul.

Interpretation

High-performing malls may indicate:

Strong brand mix

Better accessibility

Higher consumer spending power

2. Revenue by Gender
Distribution:

Female: 150.21M (59.72%)

Male: 101.31M (40.28%)

Interpretation

Female shoppers contribute a significantly larger share of spending, likely due to:

Higher purchases in clothing, cosmetics, and lifestyle categories.

More frequent mall visits.

3. Payment Method Analysis
Revenue Contribution:

Credit Card: 112.8M (44.9%)

Cash: 88.1M (35.0%)

Debit Card: 50.6M (20.1%)

Interpretation

Customers strongly prefer non-cash digital payments, indicating:

Higher trust in card payments

Larger average transaction sizes via cards

4. Category-wise Performance
Top Revenue Categories:

Clothing → ~110M

Shoes → High but lower than clothing

Technology → Strong mid-level revenue

Cosmetics → Moderate

Toys / Books / Souvenir → Low revenue contribution

Interpretation

Clothing and Shoes dominate sales—core sectors for mall-based retail.

5. Count of Payment Method vs Revenue by Category

This combined visual shows:

Clothing & Shoes: Highest transaction count and revenue

Technology: High revenue but lower transaction count (higher AOV)

Cosmetics: Quick turnover with consistent revenue

Toys/Books: Low traffic & low revenue

# 🧮 Suggested DAX Measures

Include these in your GitHub for clarity.

Total Revenue = SUM(fact_sales[price])

Total Transactions = COUNT(fact_sales[transaction_id])

Average Basket Size = 
DIVIDE(
    SUM(fact_sales[quantity]),
    [Total Transactions]
)

AOV = 
DIVIDE(
    [Total Revenue],
    [Total Transactions]
)

Revenue YoY = 
CALCULATE(
    [Total Revenue],
    DATEADD(dim_calendar[date], -1, YEAR)
)

Revenue YoY Growth % =
DIVIDE([Total Revenue] - [Revenue YoY], [Revenue YoY])

Transactions MoM % =
VAR PrevMonth =
    CALCULATE([Total Transactions], DATEADD(dim_calendar[date], -1, MONTH))
RETURN DIVIDE([Total Transactions] - PrevMonth, PrevMonth)

# 📉 Visuals Included

The Power BI report includes:

KPI Card Deck (Revenue, AOV, Basket Size, MoM/YoY metrics)

Bar Chart: Revenue by Shopping Mall

Pie Chart: Revenue by Shopping Mall, Gender, Payment Method

Vertical Bar Chart: Revenue by Category

Combined Chart: Payment Method Count + Revenue by Category

# 🎯 Business Recommendations
1. Focus on high-performing malls

Increase store count in Mall of Istanbul and Kanyon to maximize ROI.

2. Promote female-targeted campaigns

Given female dominance in spending:

Launch female-focused sales

Expand cosmetics, shoes, clothing sections

3. Expand card-based loyalty programs

Credit card transactions dominate → strong loan/EMI potential.

4. Revamp low-revenue categories

Books, Souvenir, Toys need:

Promotions

Better placement

Bundled offers

5. Strengthen technology category

High AOV but lower transaction count → big-ticket potential.

