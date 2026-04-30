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


