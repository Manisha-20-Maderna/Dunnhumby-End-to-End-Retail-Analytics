# 📊 Dunnhumby End-to-End Retail Analytics | Power BI Dashboard

## 📌 Project Overview
This project analyzes the **Dunnhumby – The Complete Journey** retail dataset using **Power BI** to uncover insights into sales performance, customer behavior, campaign effectiveness, and promotional impact. The solution integrates **8 relational datasets** through data modeling, Power Query transformations, and advanced DAX measures to build four interactive, end-to-end business dashboards.

The project simulates a real-world retail analytics engagement — from raw transactional data to executive-ready dashboards — covering sales performance, customer segmentation, marketing campaign ROI, and in-store promotion effectiveness.

---

## 📂 Dataset
**Source:**(https://www.kaggle.com/datasets/frtgnn/dunnhumby-the-complete-journey/data?utm_source=chatgpt.com&select=campaign_table.csv)

**Files Used:**
- `transaction_data.csv` — Household-level transaction log (2.5M+ rows)
- `product.csv` — Product hierarchy (department, brand, commodity)
- `hh_demographic.csv` — Household demographic profiles
- `campaign_desc.csv` — Campaign metadata (type, duration)
- `campaign_table.csv` — Household-to-campaign targeting map
- `coupon.csv` — Coupon-to-product-to-campaign mapping
- `coupon_redempt.csv` — Coupon redemption events
- `causal_data.csv` — In-store display and mailer promotional activity

---

## 🛠 Tools & Technologies
- Power BI Desktop
- Power Query (M)
- DAX (Data Analysis Expressions)
- Data Modeling (Star Schema, Relationships, Cardinality Management)
- Microsoft Excel

---

# 📈 Dashboard 1 – Executive Sales & Product Overview
**Objective:** Analyze overall business performance, sales trends, and product-level performance.

**KPIs:** Total Sales • Total Transactions • Total Quantity Sold • Average Basket Value • Total Customers • Total Discount

**Visuals:** Sales trend by quarter • Sales by department • National vs Private brand split • Product category treemap • Department performance matrix

**Dashboard Preview**

 <img src="Image/Screenshot 2026-08-03 144244.png" width="700"/>

---

# 👥 Dashboard 2 – Customer Analytics & Loyalty
**Objective:** Analyze customer demographics, purchasing behavior, and loyalty patterns.

**KPIs:** Total Households • Average Spend • Average Basket Value • Total Baskets • Repeat Customers

**Visuals:** Sales by household size • Homeownership distribution • Spend vs frequency scatter plot • Coupon redeemer vs non-redeemer comparison • Age × income sales matrix

**Dashboard Preview**

<img src="Image/Screenshot 2026-08-03 144518.png" width="700"/>

---

# 🎯 Dashboard 3 – Campaign & Coupon Performance
**Objective:** Evaluate marketing campaign effectiveness and coupon redemption performance.

**KPIs:** Total Campaigns • Targeted Households • Total Coupons • Coupons Redeemed • Redemption Rate

**Visuals:** Redemption trend by quarter • Targeted-to-redeemed funnel • Campaign duration by type • Top campaigns by redemption rate table • Targeted vs redeemed households by campaign

**Dashboard Preview**

<img src="Image/Screenshot 2026-08-03 144449.png" width="700"/>

---

# 🏪 Dashboard 4 – Promotion & Store Performance
**Objective:** Measure in-store promotional impact and store-level sales performance.

**KPIs:** Participating Stores • Total Transactions • Mailer Sales • Promoted Products

**Visuals:** Display vs No Display sales • Mailer vs No Mailer sales • Top 10 stores by sales • Quantity vs sales value scatter plot • Store × quarter sales heatmap

**Dashboard Preview**

<img src="Image/Screenshot 2026-08-03 144554.png" width="700"/> 

---


# 📊 Key Insights

<img src="Image/Screenshot 2026-08-03 144625.png" width="700"/>

- 💰 Generated **$8.06M** in sales from **276K** transactions with an average basket value of **$29.14**
- 🛒 **National Brands** contributed **72%** of total revenue, significantly outperforming Private Brands
- 👥 **Two-person households** were the highest-spending customer segment, while homeowners made up nearly two-thirds of the customer base
- 🎯 Coupon campaigns achieved a **27.4% redemption rate**, with **Type A** campaigns delivering the strongest customer response
- 🏪 **Store 367** was the highest-performing store by sales
- 📈 Sales and coupon redemptions peaked during **Q4–Q6**, indicating a stronger seasonal demand period

---

# 🔗 Data Model
The project integrates **8 interconnected tables** using relationships built on **PRODUCT_ID, household_key, CAMPAIGN, and COUPON_UPC**, forming a star-schema-style model that supports cross-filtering across all four dashboards.

**Data Model Preview**

<img src="Image/Screenshot 2026-08-03 152042.png" width="700"/>

---

# 🧩 Key Challenges & Solutions

| Challenge | Solution |
|---|---|
| Composite join key required (PRODUCT_ID + STORE_ID + WEEK_NO) with no native multi-column relationship support in Power BI | Built concatenated key columns and evaluated both relationship-based and DAX-based (SUMX/FILTER) join strategies |
| Many-to-many relationship between promotional (causal) and transactional data | Diagnosed root cause, tested multiple resolution approaches, and transparently documented the resulting data limitation instead of presenting misleading precision |
| Floating-point rounding artifacts in currency columns | Identified via column profiling and resolved using Fixed Decimal Number typing |
| Blank/unmatched categories from incomplete demographic and product joins | Investigated root cause (unmatched keys vs. true nulls) and applied targeted relabeling logic |
| High-cardinality dimensions (100+ stores, 700+ days, 5,000+ commodities) cluttering visuals | Applied Top N filtering, quarter-level time bucketing, and category grouping for readability |
| Inconsistent sort order on text-based categorical fields | Built helper "Sort by Column" fields to preserve logical ordering (e.g., household size, quarters) |

---

# 💡 Skills Demonstrated

**Technical Skills**
- Power BI Desktop (Report & Model Development)
- Power Query (Data Cleaning & Transformation)
- DAX (Measures, Calculated Columns, CALCULATE, FILTER, SWITCH, DIVIDE, SUMX)
- Data Modeling (Relationships, Cardinality, Cross-Filter Direction, Composite Keys)
- Star Schema Design
- Data Cleaning & Quality Diagnosis
- KPI Development
- Dashboard Design & UX

**Analytical Skills**
- Retail Analytics
- Customer Segmentation Analysis
- Marketing Campaign ROI Analysis
- Promotional Lift Analysis
- Root-Cause Data Diagnostics
- Business Storytelling with Data

**Tools**
- Power BI
- Power Query (M Language)
- DAX
- Microsoft Excel

---

## ⭐ Business Value
This project enables retail businesses to:
- Monitor sales performance and product trends in real time
- Understand customer purchasing behavior and segment loyalty
- Measure marketing campaign and coupon effectiveness
- Analyze store-level and promotional performance
- Support data-driven decision-making across sales, marketing, and operations teams

---

## 📁 Repository Structure
```text
📦 Dunnhumby-End-to-End-Retail-Analytics
├── Dataset
├── Images
│   ├── Dashboard1.png
│   ├── Dashboard2.png
│   ├── Dashboard3.png
│   ├── Dashboard4.png
│   ├── Key_Insights.png
│   └── Data_Model.png
└── README.md
```

---

## 📬 Contact
For questions, feedback, or collaboration opportunities, feel free to connect.
