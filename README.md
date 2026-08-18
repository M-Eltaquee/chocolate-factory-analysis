# 🍫 Chocolate Sales Dashboard – Power BI

### 🔗 [My LinkedIn](https://www.linkedin.com/in/saleh2023/)
### 📥 [Download the PBIX File](https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/Chocolate%20Sales%20Data.xlsx?raw=true)
**📄 [Full Documentation](https://htmlpreview.github.io/?https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/PROJECT-DOCUMENTATION.html)**

<br>
<div align="center">
  <img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/1Intro.png?raw=true" alt="Chocolate Sales Dashboard Cover" width="1000">
</div>

---

## 📝 Introduction
<details>
  <summary><strong>📌 Overview (click)</strong></summary>

### **Overview**
> This Power BI project analyzes sales, profitability, and sales-team performance for a chocolate distribution business across 3 regions and 22 products. It covers **revenue trends**, **regional performance**, **product profitability**, and **sales-team efficiency**, closing with a findings-and-recommendations page for leadership.
> Built end-to-end: data cleaning and modelling in Power Query, DAX measures, and an AI-assisted design pass (Claude + Claude Design) used to prototype the dashboard's visual layout before the final Power BI build.

</details>

<details>
  <summary><strong>📂 Data Sources (click)</strong></summary>

### **Data Sources**
> Provided as a single Excel workbook with 3 raw sheets, deliberately unstructured (a combined dimension sheet with 3 tables squashed side-by-side), cleaned and split in Power Query into a proper star schema.

**▼ 📑 Dataset Explanation**
1. **Fact_Sales** — ShipmentID, SPID, PID, GID, DSID, Shipdate, Quantity, Cost Per Box, Revenue
2. **Dim_Product** — PID, Product, Category, Cost_per_box
3. **Dim_Location** — GID, Geo, Region
4. **Dim_SalesMen** — SPID, Sales_person, Team, Picture
5. **Dim_Delivery** — DSID, Order_Status
6. **Dim_Calender** — cal_date (marked Date Table), Month_num, month_name, Quarter, year, weekday_num, weekday_name

</details>

---

## 🎯 Case Study
A chocolate distributor sells 22 products across 3 regions (APAC, Americas, Europe) through a team of salespeople. Leadership needed a report to answer:
- How is revenue trending, and which regions/products drive it?
- Which products are most profitable, not just highest-selling?
- Which salespeople are over- or under-performing, and where's the volume-vs-revenue disconnect?
- What should leadership act on first?

---

## 📊 Main KPIs
- **💰 Total Revenue**: $44,692,389
- **📦 Total Boxes Sold**: 3,784,002
- **💵 Avg. Cost / Box**: $6.46
- **📉 Total Cost**: $24,452,520
- **📈 Total Profit**: $20,239,869
- **🏆 Top Salesperson**: Barr Faughny ($3,664,346)

---

## ⚙️ Process
1. Imported the Excel workbook via Power Query — 3 raw sheets, one of them a deliberately unstructured combined-dimension sheet
2. Split the combined sheet into 3 clean dimension queries (Products, Locations, People); built a 6th dimension (Delivery/Order Status) that didn't exist in the source
3. Built a star-schema data model in Power BI: `Fact_Sales` at the center, 5 dimension tables, single-direction 1-to-many relationships
4. Marked `Dim_Calender[cal_date]` as the official Date Table (continuous range, no gaps) so time-intelligence measures work correctly
5. Built 14 explicit DAX measures across KPIs, Product Insights, and Salesperson Performance folders, using `DIVIDE()` throughout to guard against divide-by-zero
6. Prototyped the visual design with an AI-assisted workflow (Claude Design) — built a chocolate-themed design system (dark cocoa/gold palette) from a real content brief generated off the finished data model, then handed the approved mockup pages to Power BI Desktop as a visual reference
7. Applied a matching custom Power BI theme (colors, typography) generated from the same design system
8. Validated every measure in a plain table visual before adding it to a chart

---

## 📐 Data Model
![Data Model](https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/data%20model.png?raw=true)

---

## 📈 Dashboard Preview

**Page 1 — Overview:** revenue, boxes sold, profit, regional split, order-status distribution, and a Year→Quarter→Month drillable sales trend.
<img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/2Overview.png?raw=true" width="1000">

**Page 2 — Product Insights:** category revenue contribution, profit margin by product (collapsed by category, drill for detail), and seasonal sell-through by month.
<img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/3products.png?raw=true" width="1000">

**Page 3 — Sales Team Performance:** top/bottom 5 leaderboards and an efficiency-gap table flagging high-volume, low-revenue-per-box salespeople.
<img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/4sales%20team.png?raw=true" width="1000">

**Page 4 — Findings & Recommendations:** narrative summary of what the data shows and prioritized next steps.
<img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/5.png?raw=true" width="1000">

---

## 🎥 Project Demo
<img src="https://github.com/M-Eltaquee/chocolate-factory-analysis/blob/main/Preview.gif?raw=true" width="1000">

---

## 🔍 Key Insights
1. **APAC alone drives more than half of total revenue** — $23,595,732 (52.8% of $44,692,389 total) vs. Americas $10,554,851 and Europe $10,541,806. APAC outsells either other region more than 2-to-1, and is roughly equal to Americas + Europe combined.
2. **Bites is the smallest category by revenue but the most profitable by far** — 65.3% margin vs. Bars 35.6% and Other 42.6%, despite Bars generating almost double Bites' revenue.
3. **Six salespeople sell high volume but generate below-average revenue per box** — Jehu Rudeforth, Gunar Cockshoot, Beverie Moffet, Andria Kimpton, Camilla Castle, and Brien Boise are all above the 151,360-box average while below the $11.81 revenue-per-box average.
4. **The October 2024 revenue drop is a data artifact, not a real decline** — $17,019 vs. $2,251,733 in September (99.2% lower); the source extract simply ends mid-quarter.

---

## 💡 Conclusion
This dashboard gives leadership a clear, data-driven view of where revenue and profit are actually coming from — surfacing that Bites' margin advantage and the Americas/Europe growth gap are worth acting on before the next planning cycle, and flagging which salespeople's pricing/discounting habits merit a closer look.

---

## 🧰 Tools Used
- **Power BI Desktop**
- **Power Query**
- **DAX**
- **Data Modelling (Star Schema)**
- **AI-assisted design workflow** (Claude Design, custom Power BI theme generation)

---
## 📁 Project Structure

```bash
chocolate-factory-analysis/
│
├── 1Intro.png
├── 2Overview.png
├── 3products.png
├── 4sales team.png
├── 5.png
├── data model.png
├── Preview.gif
├── Chocolate Sales Data.xlsx
└── README.md
```
