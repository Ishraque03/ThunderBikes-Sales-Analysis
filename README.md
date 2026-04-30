# ThunderBikes-Sales-Analysis
## Project Overview

ThunderBikes is a multinational cycling company selling bikes, accessories, and clothing across the United States, Australia, United Kingdom, Germany, France, and Canada.  
This project transforms raw transactional data into a fully interactive Power BI dashboard, supported by a detailed business insight report. The analysis is structured to deliver descriptive, diagnostic, predictive, and prescriptive insights, enabling data-driven strategic decision-making at the executive level.

## Objectives

- Analyze overall sales performance and growth trends  
- Understand customer behavior and demographics  
- Evaluate product and category performance  
- Identify risks and opportunities in the business  
- Provide actionable, data-driven business recommendations  

## Dataset Used
- <a href="https://github.com/Ishraque03/ThunderBikes-Sales-Analysis/tree/main/ThunderBikes%20Dataset">Dataset</a>

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI Desktop** | Dashboard design, data modelling, and interactive visualisations |
| **Power Query (M Language)** | Data cleaning, transformation, and preparation |
| **DAX (Data Analysis Expressions)** | Custom KPI measures, time intelligence, and MoM calculations |
| **Microsoft Excel** | Initial data exploration and validation |

## Instructions

1.  Download the <a href="https://github.com/Ishraque03/ThunderBikes-Sales-Analysis/blob/main/ThunderBikes%20Sales%20Analysis%20Dashboard.pbix">ThunderBikes Sales Analysis Dashboard.pbix</a> file from the repository.
2. Open the file using **Power BI Desktop**.  
3. Navigate through the dashboard pages using navigation buttons:
   - Home  
   - Trend  
   - Customer Demographics  
   - Customer Profile  
   - Product  
4. Use slicers and filters to explore insights based on:
   - Time (Year, Month)  
   - Country / Market  
   - Product Category & Subcategory  
   - Customer segments  
5. Interact with visuals (hover, click, drill-down) to uncover detailed insights.

## Dashboard Preview

1. **Home**  
<img width="1419" height="801" alt="Home" src="https://github.com/user-attachments/assets/bba72714-d07d-4244-a8cb-5846edb30ca5" />
 
2. **Trend**  
<img width="1419" height="802" alt="Trend - Sales" src="https://github.com/user-attachments/assets/79652885-be85-4230-88fd-4c2cfa216acf" />

3. **Customer Demographics**  
<img width="1421" height="802" alt="Customer D" src="https://github.com/user-attachments/assets/ed570219-255f-458c-95d5-f89bd7895bcf" />

4. **Customer Profile**  
<img width="1419" height="802" alt="Customer P" src="https://github.com/user-attachments/assets/e0856673-c405-4043-b8d4-4f5bc466c4aa" />

5. **Product**  
<img width="1420" height="801" alt="Product" src="https://github.com/user-attachments/assets/570a3b35-458d-413b-880d-cea131aca461" />

## Data Model

The dashboard is built on a **star schema**, where a central fact table is connected to multiple dimension tables for efficient analysis and filtering.

### Fact Table
**sales_details** — Transactional sales data  
- Contains order-level information such as:
  - Customer ID (cst_id)  
  - Product Key (prd_key)  
  - Order Number (sls_ord_num)  
  - Order Date (sls_order_dt)  
  - Due Date (sls_due_dt)  
  - Sales Price & Cost (sls_price, sls_cost, prd_cost)  
  - Delivery Status  

### Dimension Tables
**Date** — Time intelligence table  
- Supports time-based analysis with:
  - Date, Day, Month, Quarter, Year  
  - Day Type, Weekday  
  - Month No., Day No.  

**cust_details** — Customer information  
- Stores customer-level attributes:
  - Customer ID (cst_id, cst_key)  
  - Full Name (cst_fullname)  
  - Gender (cst_gndr)  
  - Country (cst_country)  
  - Birthdate (cst_bdate)  
  - Account creation date (cst_create_date)  

**prd_details** — Product information  
- Defines product hierarchy and attributes:
  - Product Key (prd_key)  
  - Product ID (prd_id)  
  - Category (prd_cat, prd_cat_id)  
  - Product Line (prd_line)  
  - Cost (prd_cost)  
  - End Date (prd_end_dt_new)  

###  Relationships
- **Date → sales_details** (1-to-many)  
- **cust_details → sales_details** (1-to-many)  
- **prd_details → sales_details** (1-to-many)  

The **sales_details** table acts as the central fact table, while all dimension tables provide context for filtering and slicing the data across time, customer, and product perspectives.
<img width="1254" height="763" alt="Screenshot 2026-04-30 152824" src="https://github.com/user-attachments/assets/6cba5501-7982-43e5-a40b-06f082837fea" />


## **Business Insights**
### **Overall Business Performance**

**Revenue Milestone**

ThunderBikes has accumulated $29.4 million in total revenue across the observed period, processed through 27,700 orders from a customer base of 18,500 unique customers. The average order value stands at $1,100, indicating a premium-leaning product portfolio, consistent with a business selling high-ticket physical goods like road and mountain bicycles alongside accessories.

A 39.8% profit margin is notably strong for a product-based retail/wholesale operation in the sporting goods industry, signalling effective cost management, strong brand positioning, or a favourable product mix. Total cost stands at $17.7M against $29.4M revenue, a $11.7M gross profit pool.

**Revenue Health**

Month-on-month revenue is still growing (+0.16%), but the pace is decelerating. Order volumes are rising faster (+3.25%) than revenue, a signal that average basket size is shrinking.

**AOV Warning**

The AOV decline of 3.00% is the most urgent red flag on the dashboard. Revenue growth is being driven by order volume, not by per-order value, a structural shift that could compress margins.

**Margin Stability**

Profit margin held almost flat (+0.03%). Despite the AOV decline, cost control is keeping profitability stable but this buffer will erode if volume-driven growth continues without upselling.

**Order Volume vs Revenue**

Orders grew 20× faster than revenue this month. This divergence needs monitoring: it suggests customers are buying lower-priced SKUs (accessories, clothing) more than premium bikes.



### **Trend**

**Revenue & Sales Trends**

The big picture: From early 2011 through end-2013, ThunderBikes moved from ~$200K/month in revenue to over $2M/month — a 10× growth trajectory in roughly three years. The long-run trend line confirms this is structural, sustained growth, not a one-off spike.

**Trend Overtime**

The Sales Trend Overtime chart reveals a slow, steady climb from 2011 through mid-2012, followed by a sharp, accelerated growth phase from late 2012 into 2013. Monthly revenues break through the $1M barrier around early 2013 and approach $2M by the data's end. The dashed regression line confirms a persistent upward structural trend with no mean-reverting pattern.

Notably, the Annual Sales Trend shows that July–August represent the seasonal revenue peak (~$3M in a single month), while January–February are the trough ( ~$1.9M). This ~58% swing between off-peak and peak months is significant for cash flow planning and inventory management.

**Quarterly & Weekly Patterns**

The Quarterly Trend chart (Trend Analysis page) is highly revealing. Q4 dominates all other quarters with $9.1M in sales (Total Sales mode), nearly 1.7× Q1's $5.5M. This Q4 surge is a classic seasonal pattern for sporting goods, driven by holiday gifting and year-end promotions. Q3 ($7.6M) and Q2 ($7.1M) form a plateau, while Q1 is the clear weakest quarter.

Weekly patterns are remarkably flat. All seven days register between $4.1M–$4.3M across the full period, with Tuesday marginally leading. It means ThunderBikes doesn't suffer from weekend-collapse or Monday-slump, suggesting a healthy mix of B2B and B2C channels or a well-managed e-commerce platform operating 7 days a week.


**Seasonality & Time-Based Patterns**

Annual Seasonality Descriptive
The Annual Sales Trend chart shows a consistent pattern: January–February form a trough (~$1.9M/month), revenues build steadily through spring, peak sharply in June–July ( ~$3M), ease slightly in August–September, then resurge in November–December (holiday season). This dual-peak profile, one summer, one holiday, is classic for premium cycling brands.

The summer peak is driven by outdoor riding season in the Northern Hemisphere (US, UK, Germany, France), while the holiday peak is gifting-driven. Australia's summer (December–February) likely explains why global revenue doesn't collapse in the traditional Northern Hemisphere off-season. Australia partially offsets the winter dip.

**Day-of-Week Flatness is a Hidden Strength**

The Weekly Trend shows extremely stable daily sales ($4.1M–$4.3M range across all days for total sales; ~$3.6K–$3.8K per day for customers). This is operationally valuable: it means inventory, logistics, and staffing can be planned linearly without weekend surge capacity. It also implies a strong online/e-commerce channel brick-and-mortar retail would typically show weekend concentration.



### **Customer Demographics & Demographics**

**Customer Growth Trajectory**

ThunderBikes' customer base grew from near-zero in early 2011 to over 2,000 new customers per month by late 2013, a steep exponential ramp that mirrors the revenue curve. This suggests customer acquisition has been the primary growth engine, rather than deeper monetisation of existing customers. The dashed trend line sits below the actual curve from mid-2013 onward, indicating above-trend acceleration in customer acquisition which is likely driven by product expansions, market entry into new geographies, or heightened marketing spend.

**Demographic Profile**

**Gender split is near-perfectly balanced:** 50.79% female, 49.21% male. This is an unusually even distribution for a cycling brand. It suggests ThunderBikes has successfully avoided the "male-dominated sporting goods" trap, appealing across gender lines through product variety (clothing, accessories) and inclusive marketing.

**Marital status:** 53.43% married vs 46.57% single. Married customers slightly dominate, which aligns with higher-AOV household purchase behaviour, couples or families buying bikes together or for children, which could explain the strong Road and Standard bike categories.

**Product category preference by customer count:** Accessories attract the most unique customers (15.11K), followed by Bikes (9.13K) and Clothing (6.85K). Accessories are the gateway product. They bring customers into the ecosystem at low cost of commitment, which can then be converted to high-value bike purchases.


### **Product**



**Critical imbalance** 

Bikes represent 96.3% of revenue ($28.31M of $29.4M) but only 25.2% of quantity sold (15.2K of 60.4K units). The business is financially concentrated in one category while operationally diversified across three.

**Sales by Category**

Bikes ($28.31M) utterly dominate revenue, followed by Accessories ($0.70M) and Clothing ($0.34M). However, when viewed through the lens of quantity sold, the picture reverses entirely: Accessories lead with 36.1K units, Bikes have 15.2K, and Clothing has 9.1K. This is the classic revenue-per-unit disparity — bikes have massive per-unit value (~$1,863 per bike) while accessories average just ~$19 per unit.

**Product Line Breakdown**

Road bikes lead revenue at $14.62M, followed by Mountain ($10.25M), Touring ($3.88M), and Standard ($0.60M). But in quantity terms, Standard bikes dominate with 23.37K units — nearly as many as Mountain (16.9K) and Road (15.55K) combined. Touring has the fewest units (4.59K) but commands premium pricing.

**Top-selling products by quantity**
Tires & Tubes (17.32K), Road Bikes (8.07K), Bottles & Cages (7.99K), Helmets (6.44K), Mountain Bikes (4.97K). Worst sellers: Bike Stands (249 units), Bike Racks (327), Vests (565), Socks (568), Hydration Packs (733) — these represent chronically underperforming SKUs that tie up inventory capital.

**Cross-sell gap**
18,500 customers bought bikes but accessories generated only $700K. With 15.2K bikes sold, average accessory spend per bike transaction is ~$46 — extremely low. Every bike sale is a missed cross-sell opportunity.

**Dead inventory risk:** Bike Stands (249 units), Bike Racks (327), and Vests (565) are near-stagnant SKUs. Holding these products incurs carrying costs without returns. A clearance or bundle strategy is needed urgently.

---

### **Geographic Market Analysis**

**Two markets dominate** 
The United States ($9.16M) and Australia ($9.06M) together account for 62.0% of total revenue — a near-perfect split between them. All other markets are distant followers.

**Country-Level Revenue & Customer Distribution**

Beyond the US–Australia duopoly, the United Kingdom ($3.39M, 1.91K customers), Germany ($2.89M, 1.78K customers), France ($2.64M, 1.81K customers), and Canada ($1.98M, 1.57K customers) form a secondary tier. Note that France and Germany have similar customer counts but France generates less revenue, a subtle signal that French customers have lower AOV or buy more accessories than bikes compared to German customers.

Canada significantly underperforms relative to its economic size and English-language advantage, suggesting untapped potential or a distribution/awareness gap in the Canadian market. The UK's volume-to-revenue ratio is healthy, second only to the US, pointing to a mature, high-conversion market presence.

**Concentration Risk**

62% revenue dependence on two markets creates vulnerability.

**Expansion opportunity**

Canada, Germany, and France remain under-penetrated growth markets.


### **Diagnostic Analysis: Why It Happened**

**Why did revenue accelerate sharply from late 2012?**

Driven by geographic expansion, product scaling (especially Standard bikes), and increased marketing investment.

**Why is AOV declining while orders are growing?**

Shift toward lower-value products and higher volume of entry-level purchases.

**Why are the US and Australia so dominant?**

Strong early market entry, infrastructure, and high market penetration.

**Why are worst-selling products still in the portfolio?**

Lack of SKU rationalisation and weak product-market fit.


### **Predictive Analysis: What Comes Next**

- Revenue will continue growing, but more slowly. Growth will remain positive but at a reduced pace due to market maturity.

- Q4 2014 will be the biggest quarter yet. Seasonal demand and a larger customer base will drive record sales.

- Customer base will cross 25,000 within 12 months. High acquisition rates will rapidly expand the customer pool.

- Australia could overtake the US in revenue. Strong growth momentum may shift market leadership.

- AOV will continue declining without intervention. Product mix shift will reduce revenue quality.

- Revenue concentration risk will intensify. Dependence on key markets will increase vulnerability.

- Dead-stock accumulation will worsen. Inventory inefficiencies will grow without action.

- Customer churn risk from low-frequency buying. Low engagement may reduce long-term value.


### **Prescriptive Recommendations**

- Launch a structured bike-to-accessories cross-sell program to increase revenue per transaction through bundled offers.

- Implement an AOV recovery strategy immediately to encourage higher-value purchases via upselling tactics.

- Clear dead-stock SKUs via targeted promotions or bundles to improve inventory efficiency and free up capital.

- Launch a Q1 activation campaign to reduce seasonal revenue dips.

- Build a customer retention & loyalty programme to increase repeat purchases and lifetime value.

- Prioritise Canada, Germany, and France to diversify revenue streams geographically.

- Develop a gender-inclusive strategy to leverage balanced demographics for growth.

- Invest in upsell journeys to shift customers toward premium products.

### **Key Takeaways for Stakeholders**

ThunderBikes is a healthy, fast-growing business but must shift from acquisition to monetisation.

-  **Protect the margin:** AOV decline must be addressed to sustain profitability.

- **Accessories are a major opportunity:** High-margin segment with untapped potential.

- **Focus on retention:** Customer lifetime value is currently underutilised.

- **Plan around seasonality:** Predictable trends allow better strategic planning.

- **Diversify geographically:** Reduce dependence on top markets.

- **Fix inventory inefficiencies:** Dead stock is reducing operational performance.

## Conclusion

This project demonstrates how raw transactional data can be transformed into a comprehensive, multi-page business intelligence dashboard and how structured analytical thinking across descriptive, diagnostic, predictive, and prescriptive layers can surface actionable insights that drive real strategic decisions.
ThunderBikes is a healthy, high-growth business. The data shows a clear path forward: protect the margin, close the accessory cross-sell gap, invest in retention, and diversify geographically. The numbers tell the story — this dashboard makes it visible.

## Author

**Syed Hasan Ishraque**  
- BBA in General, Bangladesh University of Professionals  
- Aspiring Data Analyst
LinkedIn: *www.linkedin.com/in/syed-hasan-ishraque* 
