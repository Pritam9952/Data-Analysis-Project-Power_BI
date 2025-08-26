# Mobile Sales Data Dashboard (Power BI)

A professional **Power BI** dashboard project analyzing **mobile phone sales** across cities, brands, models, payment methods, and time periods.

> Built by **Pritam Nagar** · Learned from **Skill Course (Satish Dhawale)**

---

## 🚀 Highlights

- **Total Sales:** ₹769M  
- **Total Quantity:** 19K units  
- **Key KPIs:** Avg. Sales, Transactions  
- **Top Brand:** Apple · **Top Model:** iPhone SE  
- **Best Sales Day:** Saturday (~₹43.5M)  
- **Preferred Payment:** UPI (~26%)

![Dashboard Preview](./assets/dashboard.png)

---

## 📁 Project Structure

```
/Mobile-Sales-PowerBI
├── Slaes.pbix
├── README.md
└── assets/
    └── dashboard.png  
```


---

## 📊 What’s Inside the Dashboard

**Pages / Sections**
- Overview KPIs (cards)
- Quantity trend by **Month**
- **City-wise** sales (map)
- **Model-wise** sales (bar)
- **Payment method** distribution (donut)
- **Customer ratings** distribution (bar)
- **Brand table**: Quantity, Sales, Transactions
- **Day-of-week** sales trend

**Slicers**
- Month
- Mobile Model
- Payment Method

---

## 🧠 Data Model & Measures (DAX)

Below are sample/representative measures you can add or adapt inside your PBIX:

```DAX
Total Sales := SUM('Sales'[Sales Amount])

Total Quantity := SUM('Sales'[Quantity])

Average Sales := 
DIVIDE([Total Sales], DISTINCTCOUNT('Sales'[Invoice ID]))

Transactions := DISTINCTCOUNT('Sales'[Invoice ID])

Sales by Day := 
CALCULATE([Total Sales], ALLEXCEPT('Date', 'Date'[Day Name]))

MoM Sales % := 
VAR Curr = [Total Sales]
VAR Prev = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, MONTH))
RETURN DIVIDE(Curr - Prev, Prev)

YoY Sales % := 
VAR Curr = [Total Sales]
VAR Prev = CALCULATE([Total Sales], DATEADD('Date'[Date], -1, YEAR))
RETURN DIVIDE(Curr - Prev, Prev)
```

> Ensure you have a proper **Date table** marked as *Date Table* with continuous dates.

---

## 🛠️ Requirements

- **Microsoft Power BI Desktop** (latest version recommended)
- Data source tables: `Sales`, `Products/Models`, `Brands`, `Cities`, `Customers`, `Payments`, `Date`
- Relationships:  
  - `Sales[ModelID] -> Products[ModelID]`  
  - `Products[BrandID] -> Brands[BrandID]`  
  - `Sales[CityID] -> Cities[CityID]`  
  - `Sales[CustomerID] -> Customers[CustomerID]`  
  - `Sales[PaymentID] -> Payments[PaymentID]`  
  - `Sales[Date] -> Date[Date]`

---

## ▶️ How to Use

1. Open **Slaes.pbix** in **Power BI Desktop**.  
2. Interact with slicers (*Month, Model, Payment*).  
3. Hover over visuals for tooltips; right‑click for **drill‑through** where enabled.  
4. Publish to **Power BI Service** if you want to share a live version.

---

## ✅ To-Do / Future Enhancements

- Fix typos in titles: *“Total Quantity by Month”*, *“Transactions”*.  
- Add **MoM / YoY** trend cards & conditional formatting.  
- Include **Profit** and **Margin** if cost data is available.  
- Add **Drill-through** pages for Brand and City details.  
- Standardize a **color palette** and theme file (`.json`).

---

## 🖼️ Social Media

Use this caption for LinkedIn:

> I built a **Mobile Sales Data Dashboard** in **Microsoft Power BI** to turn raw data into actionable insights—city, brand, model, payment, and time trends in one view.  
> Thanks to **Satish Dhawale (Skill Course)** for the practical guidance.  
> #PowerBI #DataAnalytics #BusinessIntelligence #DashboardDesign

---

## 🙏 Credits

Learning guidance: **Satish Dhawale** (Skill Course)  
Project & design: **Pritam Nagar**

---

