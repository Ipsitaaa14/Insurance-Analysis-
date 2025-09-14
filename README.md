## 📊 Insurance Premium & Claims Analysis 
This Power BI project analyzes insurance claims, net profits, and premium distribution across multiple insurers and product types. The dashboard provides insights into financial performance, loss trends, and product-wise premium contributions.

## 🔍 Project Objective
- To provide an interactive financial performance dashboard for insurers. The analysis enables stakeholders to:
- Track claims and their monetary impact by type of loss.
-Compare net profits across insurers.
-Monitor premium growth trends over time.
-Identify product lines contributing the most to revenue.

## Dataset
![Dataset](Account_Table.csv)
![Dataset](Policy_Table.csv)
![Dataset](Insurer_Table.csv)
![Dataset](Product_Table.csv)
![Dataset](Premium_Commision_Table.csv)

## 📂 Dashboard Pages
![Dashboard Screenshot](Report-page-1.png)
![Dashboard Screenshot](Report-page-2.png)

## 1️⃣ Dashboard Overview
- KPIs
- Total Claims Count
- Total Claim Amount
- Net Profit by Insurer
- Premium Distribution by Product Type

## Visuals
- Claims Overview: Count & sum of claim amounts by type of loss (Accident, Fire, Liability, Theft, Natural Disaster).
- Net Profit by Insurer: Horizontal bar chart comparing insurer profitability.
- Premium Distribution: Pie chart showing product-wise percentage of total premium (e.g., Property, Legal Expense, EBI).
- Insurer Filter: Slicer to dynamically view insurer-specific data.

## 2️⃣ Premium Overview
-KPIs
- Net Premium (per insurer, per month)
- Net Profit (monthly and cumulative)
- YTD Performance

## Visuals
- Detailed Premium Table: Year, quarter, insurer details, net premium, net profit, YTD values.
- Trend Analysis: Bar chart of total premium amount by month (StartDate).
- Time Filter: Year slicer for dynamic filtering (2020–2028).
- Page Navigation: Interactive buttons to move between overview and premium pages.

## ⚠️ Challenges Faced
- Data Cleaning & Transformation
- Claims and premium data contained inconsistent date formats, requiring preprocessing.
- Large monetary values needed standardization into millions for clarity.
- Complex DAX Measures
- YTD, Net Profit, and Premium Amount calculations required advanced time intelligence functions.
- Ensuring accuracy in profit margins across insurers required calculated columns and measures with SUMX and CALCULATE.

## Navigation & Design
- Created seamless navigation between Dashboard Overview and Premium Overview using bookmarks and buttons.
- Designed visuals to balance financial KPIs with loss trend insights while maintaining clarity.

## Data Modeling
Managed relationships between multiple entities (Claims, Premiums, Insurers, Products) to ensure correct cross-filtering.

## ✅ Conclusion
- The Insurance Premium & Claims Analysis Dashboard provides a comprehensive view of insurer performance, premium contributions, and claim distribution. Key takeaways include:
- Identification of loss-heavy categories (e.g., Theft, Liability).
- Clear visibility into profitable insurers (Zurich, Chubb, Starr leading in net profit).
- Recognition of Property Insurance as the highest revenue-contributing product line.

## This dashboard supports:
- Financial planning and insurer benchmarking.
- Strategic product focus for maximizing premium revenue.
- Risk assessment through claims and loss tracking.

## 📊 Sample KPIs (DAX Measures)
Total Premium = SUM('Premiums'[PremiumAmount])

Net Profit = SUM('Premiums'[NetProfit])

YTD Premium = 
TOTALYTD(
    SUM('Premiums'[PremiumAmount]),
    'Premiums'[StartDate]
)

Total Claims = DISTINCTCOUNT('Claims'[ClaimID])

Total Claim Amount = SUM('Claims'[ClaimAmount])
