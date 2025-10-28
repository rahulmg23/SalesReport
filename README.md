# Bike Sales Analysis Report

## Overview
This project analyzes bike sales data to uncover customer purchasing patterns across demographics, commute distances, and income levels.  
The goal is to identify key factors influencing sales and provide data-driven recommendations for marketing and product strategies.

---

## ** Business Objective**

The goal is to transform existing static Excel sales reports into **interactive Power BI dashboards** to:

- Monitor **Internet Sales performance** over time  
- Identify **top-selling products** and **key customers**  
- Compare **actual sales vs. budget targets**  
- Provide **filtering options** for customers, products, and salespersons  
- Enable **data-driven decision-making** through visual insights  

---

## **3. Business Problems and Challenges**

### **3.1 Reporting Inefficiencies**
- Manual Excel-based reporting is **time-consuming** and **error-prone**.  
- Data from multiple sources (CRM, website, budget sheets) is **not unified**.  
- Sales managers spend hours compiling reports instead of analyzing performance.

---

### **3.2 Lack of Real-Time Visibility**
- Sales data is only updated **monthly or weekly**.  
- No automated **daily refresh process** for performance tracking.  

---

### **3.3 Limited Analytical Insights**
- Reports provide totals but **no trend analysis or product segmentation**.  
- Underperforming areas are difficult to identify quickly.  
- No **comparative historical data visualization** for performance review.  

---

### **3.4 Customer and Product Blind Spots**
- Sales representatives can’t easily focus on their **assigned customers or products**.  
- No segmentation or insight into **repeat buyers vs. inactive customers**.  

---

### **3.5 Budget Comparison Gaps**
- Budget data exists in Excel but lacks **automated variance analysis**.  
- Decision-makers can’t see how **actuals compare with planned targets** in real time.  

---

### **3.6 Delayed Decision-Making**
- Management often receives **outdated reports**.  
- Lack of interactive **visualizations** makes it hard to spot trends or exceptions promptly.  

---

## Tools and Technologies
- Excel – Data cleaning and pivot analysis  
- SQL Server – Querying and data manipulation  
- Power BI – Dashboard and visualization

---

## Data Cleaning and Preparation
Performed in Excel and SQL Server:
- Removed duplicates, null values, and blank columns  
- Standardized categorical fields such as gender, region, and marital status  
- Converted income and distance to consistent formats  
- Created calculated columns for commute groups and age brackets

---

## Exploratory Data Analysis (EDA)
Key insights from Excel pivot tables and SQL queries:

| Insight | Observation |
|----------|--------------|
| Gender | Males account for approximately 58% of total purchases |
| Income | Higher-income individuals (> $60K) show a greater tendency to buy bikes |
| Commute Distance | Customers with shorter commutes (0–10 miles) are more likely to purchase bikes |
| Region | Urban and suburban regions record stronger sales compared to rural areas |
| Age Group | Middle-aged customers (31–45 years) form the majority of bike buyers |

---

## Power BI Dashboard Highlights
Developed an interactive dashboard including:
1. Bar Chart – Bike Purchase by Gender  
2. Pie Chart – Bike Purchase by Region  
3. Line Chart – Relationship between Age and Average Income  
4. Slicers – Filters for Gender, Marital Status, and Commute Distance

---

## **4. Data Model and Schema Design**

The data model follows a **Star Schema** architecture, designed for efficient reporting and easy analysis in Power BI.  
It consists of **dimension tables** that provide descriptive attributes and **fact tables** that store measurable business data.

### **4.1 Data Model Overview**

![Data Model](c5cc6477-fe38-4068-b54e-26d4fe29bba2.png)

---

### **4.2 Tables Description**

#### **Dimension Tables (DIM)**
| Table | Description |
|--------|--------------|
| **DIM_Calendar** | Stores all date-related fields used for time-based analysis (Day, Month, Quarter, Year). |
| **DIM_Customers** | Contains customer details such as Name, City, Gender, and Date of First Purchase. |
| **DIM_Products** | Holds product-related information including Category, Color, Line, Model Name, and Size. |

#### **Fact Tables (FACT)**
| Table | Description |
|--------|--------------|
| **FACT_InternetSales** | Main transactional table capturing each sales record with metrics like Sales Amount, Order Date, and Customer/Product keys. |
| **FACT_Budget** | Contains budgeted values for each period to enable comparison against actual sales. |

#### **Analysis Metrics**
| Table | Description |
|--------|--------------|
| **Analysis Metrics** | Aggregated measures such as Sales and Budget to facilitate KPI tracking and performance measurement. |

---

### **4.3 Relationships**

- **DIM_Calendar** connects to both `FACT_InternetSales` and `FACT_Budget` using the `DateKey` field.  
- **DIM_Customers** connects to `FACT_InternetSales` using `CustomerKey`.  
- **DIM_Products** connects to `FACT_InternetSales` using `ProductKey`.  
- Relationships are **one-to-many (1:* )**, ensuring proper data filtering and aggregation in Power BI.

---

### **4.4 Model Highlights**

- Optimized for **time intelligence calculations** (e.g., Year-to-Date, Month-over-Month).  
- Enables **budget vs. actual sales variance analysis**.  
- Supports **dynamic filtering** by Product, Customer, and Time Period.  
- Ensures **data normalization** and reduces redundancy for better performance.

---
---

### Insights from the Dashboard

# **Sales Report**

## **The Bike Business Performance (2019–2021)**

![Bike Sales Dashboard](https://github.com/user-attachments/assets/01837dc8-247b-4469-adb5-884fc99acec7)

The company achieved **$5.797 million in yearly sales**, reflecting strong market reach and sound planning. However, heavy reliance on a single product line introduces substantial risk and operational volatility. To sustain growth, diversification and smarter demand planning are essential.

---

### **1. Financial Health and Concentration Risk**

Achieving the **$5,797,224** target underscores strategic execution — yet the business foundation remains fragile.

* **Product Dependency:** 99.5% of revenue comes from bikes, meaning any disruption in trends, supply, or competition could heavily impact income.
* **Accessories Neglected:** Accessories contribute just **0.04%** of total sales — a missed opportunity for cross-selling and higher order value.
* **Geographic Spread:** Sales span multiple U.S. cities, which helps reduce local economic risk but doesn’t offset product concentration risk.

---

### **2. Operational Volatility and Supply Chain Priorities**

Sales trends fluctuate seasonally, requiring sharper planning in both inventory and staffing.

* **Seasonal Surge:** Sales rise sharply between **October and December**, driven by holiday demand.
* **Top Performers:** Mountain and Touring bikes dominate — models like *Mountain-200 Black* and *Touring-1000 Blue* are consistently strong sellers.
* **Forecasting Gap:** February sales dipped to **$771,349**, below the **$800,000** goal — emphasizing the need for month-wise forecasting precision.
* **Stock Strategy:** Maintain higher inventory for peak-season items, and closely manage storage during off-peak months to control costs.

---

### **3. Customer Value and Retention**

Top customers significantly influence revenue performance.

* **High-Value Clients:** *Jordan Turner* generated **$11,484**, with nine other clients exceeding **$9,500** each.
* **Retention Focus:** Shifting emphasis from acquisition to retention will drive sustainable revenue.
* **Loyalty Strategy:** Predict repurchase behavior and offer benefits like early access to new models and loyalty rewards to retain high-value buyers.

---

### **Strategic Imperatives**

1. **Diversify Revenue Streams:** Introduce and promote accessories through bundles, follow-ups, and targeted ads to raise non-bike sales.
2. **Inventory Readiness:** Stock key models (top 5 sellers) well ahead of the September–December surge.
3. **Customer Retention Program:** Build a premium tier for the top 50 customers, offering exclusive access and personalized services.

---

## **Marketing Performance Review & Strategic Re-Focus**

![Marketing Dashboard](https://github.com/user-attachments/assets/906cff28-7e40-4444-ac22-03ef24f2b020)

Marketing efforts yielded **15,820 leads**, surpassing the goal by **31%** — yet conversions remain low. The issue isn’t volume, but **lead quality and cost discipline**.

| **Finding**                         | **Data Evidence**                                                                 | **Strategic Impact**                                                                                   |
| ----------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Volume Success, Quality Failure** | Lead volume exceeded the goal by **31.83%**, yet conversions stayed below **5%**. | High-volume campaigns (Email/Social) produce low-intent leads, wasting sales effort and inflating CAC. |
| **Inconsistent Campaign ROI**       | CPL vs. Conversion Rate plot shows wide cost variation for similar results.       | Budget inefficiencies across campaigns lower overall ROMI.                                             |
| **Underused High-Quality Sources**  | Referral and Social Opt-in channels are underrepresented in total leads.          | Missing out on organic, high-intent, low-CAC leads.                                                    |
| **Channel Dominance**               | Email and Social drive most leads; Webinars likely yield stronger conversions.    | Shift investment toward education-based, conversion-focused channels.                                  |

---

### **Marketing Strategic Imperatives**

1. **Prioritize Lead Quality:** Implement a lead-scoring system; align Marketing and Sales on qualification criteria.
2. **Optimize Spend:** Cut underperforming ads and reallocate funds toward webinars and referral programs.
3. **Improve Nurture Process:** Analyze drop-off points and test new website experiences and follow-up campaigns.

---

## **Product Performance and Sales Concentration (2020)**

![Product Sales Dashboard](https://github.com/user-attachments/assets/28f22ade-6b47-472c-8bc2-958302dbd23d)

Bikes dominate the portfolio, delivering **$16.35 million** in sales — exceeding the **$15.3 million** target. While this shows strong demand, it also exposes a risky over-reliance on a handful of products.

---

### **Key Financial & Product Drivers**

* **Total Revenue:** $16.35M achieved vs. $15.3M planned.
* **Top Products:** *Mountain-200* and *Mountain-300* series alone contribute ~$4.6M.
* **Customer Trend:** Premium buyers prefer high-end mountain and touring bikes — strong value segment.

---

### **Operational Insights**

* **Seasonal Peaks:** Sales peak September–December; maintain sufficient stock during this window.
* **Off-Season Dips:** February shortfall ($771K vs. $800K target) highlights the need for promotional campaigns in low months.
* **Geographic Spread:** Sales are well distributed across major U.S. cities — strong national presence.

---

### **Strategic Imperatives**

1. **Diversify Product Portfolio:** Develop accessory, apparel, or e-bike categories to reduce dependence on the top 5 bike models.
2. **Improve Forecasting Accuracy:** Align inventory planning with seasonal trends to prevent stockouts.
3. **Stimulate Off-Peak Sales:** Launch seasonal promotions like *spring tune-up* or *off-season bundles* to maintain steady cash flow.

---


## Key Performance Indicators (KPIs)

| KPI | Value | Description |
|------|--------|-------------|
| Total Bikes Purchased | 483 | Total number of units sold |
| Conversion Rate | 38% | Percentage of total customers who purchased |
| Average Income (Buyers) | $59,000 | Mean annual income of bike buyers |
| Average Commute Distance | 8.2 miles | Typical commute distance of bike buyers |

---

## Business Recommendations
- Focus marketing efforts on middle- to high-income professionals with short commutes  
- Introduce city-focused commuter bikes  
- Offer family-oriented discounts for married customers  
- Prioritize urban and suburban markets for sales expansion

---

## Summary
This analysis provides clear insights into the demographics and lifestyle factors driving bike purchases.  
Using Excel, SQL, and Power BI, this project demonstrates how effective data cleaning, analysis, and visualization can lead to strategic business decisions.
