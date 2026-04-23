# Commercial Performance Dashboard 2024-2025 | Andes Retail Group

**Link to Interactive Dashboard:** [View on Tableau Public](https://public.tableau.com/app/profile/macarena.hulsken/viz/andes-retail-performance/Diagnosticocomercial)

## 📌 Project Overview
As a Data Analyst for Andes Retail Group (a retail company operating in Peru, Chile, and Colombia), I was tasked with transforming dispersed transactional data into a clear, actionable visual narrative. 

The objective of this project is to understand the commercial performance across 2024–2025, analyzing revenue, profitability, customer behavior, and regional differences to detect strategic business opportunities.

### 🛠️ Tools & Technologies
* **Data Visualization:** Tableau
* **Data Cleaning & Preparation:** Excel / Power Query
* **Analytical Framework:** SCQA Model (Situation, Complication, Question, Answer)

---
Dataset
## 📂 Data Dictionary & Calculated Fields

The dataset contains transactional sales records for Andes Retail Group from 2024 to 2025. Below is a description of each field:

| Column | Data Type | Description | Example |
| :--- | :--- | :--- | :--- |
| **order_id** | Integer | Unique identifier for each order | 1 |
| **customer_id** | Categorical | Unique identifier for the customer | C8382 |
| **order_date** | Date | The date the sale was processed | 29/10/2025 |
| **customer_segment** | Categorical | Customer type based on commercial value (Premium, Standard, Economy) | Standard |
| **country** | Categorical | Country where the sale took place (Peru, Chile, Colombia) | Colombia |
| **region** | Categorical | Geographical region within the country (North, Central, South) | South |
| **product_category** | Categorical | Type of product sold (Electronics, Clothing, Sports, Home) | Home |
| **season** | Categorical | Season of the year (Southern Hemisphere): Summer, Autumn, Winter, Spring | Spring |
| **units_sold** | Integer | Quantity of units sold | 7 |
| **unit_price** | Decimal | Price per individual unit | 67.00 |
| **revenue** | Decimal | Total sales amount (Unit Price × Units Sold) | 469.00 |
| **cost** | Decimal | Cost associated with the sale | 325.44 |
| **Benefit** | Decimal | Calculated field representing total profit: `[Revenue] - [Cost]` | 143.56 |
| **avg_unit_price** | Decimal | Calculated field representing average price per unit: `SUM([Revenue]) / SUM([Sold Units])` | 67 |
| **average_revenue** | Decimal | Calculated field representing Average Order Value (AOV): `SUM([Revenue]) / COUNTD([Order Id])` | 469 |
| **benefit_margin** | Decimal / % | Calculated field representing profit margin percentage: `(SUM([Revenue]) - SUM([Cost])) / SUM([Revenue])` | 0.306098081 |
| **revenue_2024** | Decimal | Level of Detail (LOD) expression for fixed total revenue in 2024: `{ FIXED : SUM(IF YEAR([Order Date]) = 2024 THEN [Revenue] END) }` | 2863384 |
| **revenue_2025** | Decimal | Level of Detail (LOD) expression for fixed total revenue in 2025: `{ FIXED : SUM(IF YEAR([Order Date]) = 2025 THEN [Revenue] END) }` | 2668610 |
| **YoY_growth** | Decimal / % | Calculated field for Year-over-Year growth rate: `(ZN(SUM([revenue_2025])) - ZN(SUM([revenue_2024]))) / ZN(SUM([revenue_2024]))` | -0.068022312 |

---

## 📊 Executive Summary (SCQA Framework)

### 1. General Overview
* **Situation:** 2024 closed with a total revenue of $2.86M and a profit margin of 35.13%, with Peru leading revenue generation ($1.14M).
* **Complication:** In 2025, the landscape contracted: revenue dropped to $2.67M (35.07% margin), representing a Year-over-Year (YoY) decline of -6.80%.
* **Question:** Which segments or regions drove this revenue decline?
* **Answer:** The decline is primarily explained by the Premium segment, which generated $0.20M less in 2025, surprisingly matching the levels of the Standard segment. Regionally, although Peru remains the leader, it suffered a significant contraction (from $1.14M to $1.02M).

### 2. Detailed Diagnostic
* **Situation:** In 2025, the Sports and Home categories were the pillars of the business, jointly contributing approximately $1.40M. Seasonally, strong sales volume was driven during the summer months.
* **Complication:** There are three critical focus areas: 
  1. The Electronics category suffered a YoY decline (from $0.75M to $0.66M).
  2. Sales drop drastically during cold months.
  3. The Economy segment has a marginal business share.
* **Question:** What commercial actions can we implement to mitigate these seasonal drops and reactivate lagging segments?
* **Answer (Recommendations):**
  * **Electronics:** Deploy retargeting campaigns and targeted promotions to stimulate demand.
  * **Seasonality:** Create a winter promotional calendar or boost the "Clothing" category with a higher Average Order Value (AOV) to offset the low volume of the cold season.
  * **Economy Segment:** Conduct a pricing audit (benchmarking) of our entry-level products to understand if we are priced out of the market and why we are not capturing this customer profile.

---

## 📩 Stakeholder Communication (Slack Update)

**Subject: Commercial Performance Update (2024 vs 2025)**

Hi team 👋, 

Sharing the key insights from our recent commercial performance analysis (2024 vs 2025) and recommended next steps:

📉 **Context & Problem:**
We closed 2025 with a YoY revenue decline of -6.80%. The main drivers of this contraction are:
* **Premium Segment:** A drop of $0.20M compared to the previous year.
* **Core Market (Peru):** Revenue deceleration (dropped from $1.14M to $1.02M).
* **Categories:** Electronics suffered a YoY contraction of $0.09M.
* **Seasonality:** Overall sales drop drastically during the winter months.

🎯 **How do we reverse this trend?**
To recover volume and leverage underexploited opportunities, I suggest acting on three fronts:
1. **Mitigate Winter Drop:** Increase targeted marketing campaigns and promotions during cold months.
2. **Economy Segment Review:** Audit the pricing of our entry-level products; they currently generate very low revenue and represent a clear market opportunity.
3. **Premium Segment Deep-Dive:** Investigate the exact causes of the drop in this sector to develop retention strategies.

You can find the complete details in the attached Tableau dashboards. I am available to dive deeper into any of these points. 

Best regards!
