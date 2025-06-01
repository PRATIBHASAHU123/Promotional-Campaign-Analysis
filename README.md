# 📊 Promotional Campaign Performance Dashboard

A Power BI dashboard analyzing the effectiveness of different promotional strategies (Discounts, Cashback, BOGOF) across various product categories, stores, and campaigns.

## 🎯 Objective

To evaluate how different promotion types influence revenue, product sales, and store performance using real-world-like retail event data.

## 🧾 Dataset Overview

- `fact_events.csv` – Sales events data (before & after promotion)
- `dim_products.csv` – Product details (category, name)
- `dim_stores.csv` – Store info (city, region)
- `dim_campaigns.csv` – Campaign names and IDs


## 📌 Key Business Questions Answered

- Which promotion type drives the highest revenue (IR%)?
- Which stores perform best or worst during campaigns?
- Which product categories benefit most from each promo type?
- How do unit sales (ISU%) change before and after campaigns?


## 📈 Report Highlights

- **Interactive filters** for Campaign, City, Category
- **Top/Bottom 10 Stores** by IR% and ISU%
- **Promotion Type Performance** comparison
- **Matrix of Category × Promotion Type** with IR% and ISU%
- **KPI Cards** with Total Revenue, Avg IR%, Avg ISU%


## 🛠️ Tools Used

- Power BI  
- DAX  
- Excel (for initial data shaping)

## 📊 Key DAX Measures

IR % = 
DIVIDE(
    SUMX(fact_events, base_price * quantity_sold(after_promo)) -
    SUMX(fact_events, base_price * quantity_sold(before_promo)),
    SUMX(fact_events, base_price * quantity_sold(before_promo)),
    0
) * 100

ISU % = 
DIVIDE(
    SUM(fact_events[quantity_sold(after_promo)]) - SUM(fact_events[quantity_sold(before_promo)]),
    SUM(fact_events[quantity_sold(before_promo)]),
    0
) * 100

## 💡 Sample Insights

- 🥇 BOGOF had the highest IR% but lowest ISU%.
- 📉 South Zone underperformed despite multiple campaigns.
- 🧴 Personal Care saw strong performance under Cashback.
- 🏪 Top 3 stores contributed to over 30% of campaign lift.


## 🙋‍♀️ Created By

**Pratibha Sahu**  
🔗 LinkedIn: https://www.linkedin.com/in/pratibhas-sahu-data-analyst
💻 GitHub: https://github.com/PRATIBHASAHU123


## 📁 Project File

🔗 Download `INSIGHTS.pbix` and datasets from this repository to explore the full dashboard.
