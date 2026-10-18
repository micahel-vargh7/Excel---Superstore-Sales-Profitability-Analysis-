## Project Background

Superstore is a retail company that sells Furniture, Office Supplies, and Technology to customers across four US regions. Sales are high, but profit looks thin compared to sales. This project looks at order data from 2011 to 2014 to find where the business makes money, where it loses money, and what to do about it.

Insights and recommendations are on these five business questions:

1. Which region makes the most profit, and which one loses money?
2. Which product category has the highest sales but the lowest profit margin?
3. Is there a seasonal pattern in sales?
4. Which customer segment should the business prioritize?
5. What do the bottom 10% of products look like, and should they be cut?

**Tools used:** Excel (Pivot Tables, Pivot Charts, Slicers, Conditional Formatting, formulas).

An interactive Excel dashboard is included [here](https://1drv.ms/x/c/cda12435457f4f41/IQDmAC98gBKnT5iqWwh-sH8-AZleJYIy7ZvW_GZtHXPJvXg?e=6ESWhY&nav=MTVfezAwNDA2MDVDLUNEOTctNEY1MC05NEExLUJGMzIzRjIwMERDQX0).

## Data Structure & Initial Checks

The dataset has **9,764 rows and 21 columns:** order and ship dates, ship mode, customer, segment, location, region, product, category, sub-category, **Sales, Quantity, Discount, and Profit.**

**Grain:** one row = one line item inside an order (not one order). The same Order ID can appear many times.

Cleaning steps:

- Removed duplicate rows.
- Fixed mixed date formats. Some dates were real dates (mm/dd/yyyy) and some were text (dd-mm-yyyy). I rebuilt them with DATE(RIGHT, MID, LEFT) and pasted back as values.
- Removed extra whitespace and fixed name formatting with PROPER().
- Checked Region, Segment, Category, Sub-Category, and Ship Mode for spelling problems. None found.
- Added Year and Season columns for the seasonal analysis.
- Kept the raw data on a separate sheet and worked on a copy.
## Executive Summary

The business is profitable, but it keeps only **12.5%** of every sales dollar **($286K profit on $2.3M sales)**. All four regions are profitable, but **Furniture earns only a 2.5% margin**, and **184 products (the bottom 10%) all lose money**. The 10 worst products alone lost **$29.5K**.

## Insights Deep Dive
#### **1. Regional Performance**
- **West** makes the most profit ($108K). **Central** makes the least ($40K).
- No region is losing money. All four are profitable.
- Central sells $501K but keeps only about **8%** as profit. That is the weakest conversion of the four regions.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/dc5f099f-5727-4df8-86a5-6246005c919e" />

#### **2. Category Performance**
- **Technology** has the highest sales ($836K). **Furniture** has the lowest profit margin.
- Margins: **Furniture 2.5%**, Office Supplies 17.0%, Technology 17.4%.
- Furniture sells $742K but keeps only $18K as profit.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/8835fb18-4a75-47a9-a7ca-2461b5e08612" />

#### **3. Seasonal Pattern**
- **Fall (Sep–Nov)** is the strongest season: $104.6K profit, about **36% of all profit.**
- **Summer (Jun–Aug)** is the weakest: $56.3K profit.
- Winter and Spring are almost equal (about $62.5K–$62.9K profit).
- Margins stay close across seasons (12%–13%). The difference comes from sales volume, not efficiency.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/24178c8e-ffd3-4155-976e-86ee88461e0e" />

#### **4. Customer Segment**
- **Consumer** brings the most sales and the most profit, at about a 12% margin.
- **Home Office** has the best margin (14%) but the smallest sales and profit, so it moves the business less.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/b679aab3-51d8-40b4-9167-37ffbd125f9d" />
  
#### **5. Bottom 10% of Products**
- Profit was summed by product first (1,841 unique products), because one product appears in many rows.
- The bottom 10% is **184 products**, and **all of them have negative profit.**
- The top 10 biggest losers lost **$29.5K** together. The worst is the **Cubify CubeX 3D Printer (Double Head), at -$8.9K.**
- Those 10 products are 4 Technology, 4 Furniture, and 2 Office Supplies.
<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/dcb65ed5-8aa8-4777-b65f-9a1d8f4e0712" />

# Recommendations
- **Prioritize the Consumer segment.** It is the largest source of sales and profit.
- **Cut or fix the 10 biggest loss-making products first.** Start with the CubeX 3D printers and the Lexmark printer. Products with tiny losses (like a -$4 item) should be checked on price and cost before cutting.
- **Review Furniture pricing and discounts.** Furniture has the lowest margin and 4 of the 10 worst products.
- **Look closely at Central.** It has high sales but low profit conversion.
- **Plan marketing and stock around Fall**, the season that brings the most profit.
# Assumptions and Caveats
- The dataset has no cost column. Profit was used as given.
- Discount and Quantity were not analyzed. Discounts may explain the Furniture and loss-making product results, but this was not tested here. It is the next step.
- "Bottom 10%" was defined by **total profit per product**, not by margin.
- Results are based on 2011–2014 data and may not reflect current performance.
- This is a personal project on a public dataset (Superstore, from Kaggle).
