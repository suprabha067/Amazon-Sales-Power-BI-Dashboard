# Amazon Sales Power BI Dashboard

A professional, production-ready Power BI dashboard analyzing Amazon sales data from 2019-2024.

## 📊 Project Overview

**Dataset:** 5,000 sales transactions | **Period:** Jan 2019 - Dec 2024 | **Total Sales:** $5.9M | **Profit Margin:** 34.8%

This dashboard provides comprehensive sales analytics with executive and operational views. Features 2 interactive sheets, 10+ visualizations, 10+ DAX measures, and real-time filtering.

---

## 📋 Dataset Information

### Dataset Structure
- **File:** `amazon_sales_dataset_2019_2024_corrected.xlsx`
- **Records:** 5,000 transactions
- **Columns:** 15 (Order ID, Date, Customer, Region, Category, Product, Quantity, Price, Discount, Salesperson, Payment Method, Status, Sales, Profit)

### Key Dimensions
- **Regions:** Asia, North America, South America, Australia, Europe (5 total)
- **Categories:** Beauty, Books, Clothing, Electronics, Furniture, Home & Kitchen, Sports, Toys (8 total)
- **Salespeople:** 20 reps
- **Products:** 964+ unique products
- **Payment Methods:** Credit Card, PayPal, Amazon Pay, Debit Card, Digital Wallet (5 total)
- **Order Status:** Completed (94.2%), Pending (3.5%), Cancelled (1.2%), Returned (1.1%)

### Key Metrics
| Metric | Value | Insight |
|--------|-------|---------|
| Total Revenue | $5,935,727 | 6-year sales |
| Total Orders | 5,000 | Transaction volume |
| Avg Order Value | $1,187 | Deal size |
| Total Profit | $2,065,363 | Bottom line |
| Profit Margin | 34.8% | Profitability |
| Completion Rate | 94.2% | Order success |
| Return Rate | 1.1% | Product quality |

---

## 🎯 Dashboard Features

### Sheet 1: Dashboard (Executive Overview)
- **5 KPI Cards:** Total Sales, Orders, AOV, Profit, Profit Margin %
- **3 Charts:** Salesperson Rankings, Category Sales, Profit by Category
- **4 Slicers:** Salesperson, Region, Order Status, Category
- **Data Table:** Complete breakdown by salesperson and category

### Sheet 2: Performance Analysis (Operational)
- **5 KPI Cards:** Top Salesperson, Avg Discount, Profit Margin, Total Products, Quantity Sold
- **3 Charts:** Top 10 Salespeople, Category Sales, Profit % by Category
- **4 Slicers:** Same as Sheet 1 for consistent filtering
- **Data Matrix:** Detailed salesperson × category analysis

### Design
- **Colors:** Amazon-branded (#FF9900 orange, #232F3E dark blue, #FFFDE7 light yellow)
- **Features:** Professional layout, interactive filtering, print-ready, mobile-friendly

---

## 🚀 Quick Start

### Prerequisites
- Power BI Desktop (Latest version)
- Excel data file

### Installation
1. Clone/Download the repository
2. Open `Amazon_Sales_Dashboard.pbix` in Power BI Desktop
3. Update data source if needed: File → Options → Data Source Settings
4. Refresh data
5. Explore both sheets

### How to Use
- **For Executives:** View Sheet 1 for KPIs and trends
- **For Managers:** View Sheet 2 for team performance and category analysis
- **Interactive Features:** Click slicers to filter all visuals, hover over charts for details

---

## 📁 Files Included

```
amazon-sales-dashboard/
├── Amazon_Sales_Dashboard.pbix        (Main dashboard)
├── amazon_sales_dataset_2019_2024_corrected.xlsx  (Data source)
├── README.md                          (This file)
├── DAX_Queries.md                     (50+ measures)
└── LICENSE                            (MIT License)
```

---

## 📊 DAX Measures

**10+ measures included covering:**
- Basic KPIs (Total Sales, Orders, Profit, Margins)
- Order Status Analysis (Completion, Return, Cancellation rates)
- Sales by Dimension (Region, Category, Salesperson, Payment Method)
- Performance Metrics (Averages, Aggregations, Ratios)
- Ranking & Top Performers
- Time-based Analysis (Year, Month, MTD, YTD)
- Year-over-Year Growth
- Conditional Measures

See `DAX_Queries.md` for complete list with formulas.

---

## 🎨 Design & Branding

**Color Scheme:**
- Primary Orange: #FF9900 (Charts, highlights)
- Dark Blue: #232F3E (Headers, text)
- Light Yellow: #FFFDE7 (Background)
- Accent Green: #00B050 (Positive metrics)
- Accent Blue: #1976D2 (Secondary elements)

**Features:**
- Professional Amazon-branded design
- Consistent color scheme
- Clean, organized layout
- Interactive filtering
- Print and mobile friendly

---

## 📈 Key Insights

✅ **Sales Performance:** Track revenue by region, category, and salesperson
✅ **Team Analytics:** Identify top performers and team rankings
✅ **Profitability:** Monitor profit margins by product category
✅ **Order Health:** Track completion rates, returns, and cancellations
✅ **Discount Impact:** Analyze discount strategies and their effects
✅ **Trend Analysis:** View year-over-year growth and monthly trends

---

## 💾 Data Quality

- ✅ Verified accuracy - All calculations cross-checked
- ✅ No missing values - All fields populated
- ✅ Consistent formatting - Proper data types
- ✅ Valid date ranges - 2019-2024 period
- ✅ Cross-checked totals - Summary figures validated
- ✅ Production-ready - Suitable for real business use

---

## 🔒 License

This project is licensed under the MIT License - see LICENSE file for details.

---

## 📧 Support

For questions or issues:
- Check DAX_Queries.md for measure documentation
- Review dashboard for interactive features
- Refer to design guidelines for customization

---

## ✨ Project Status

**Status:** ✅ Production Ready

- [x] Dashboard design and development
- [x] Data integration and validation
- [x] 50+ DAX measures
- [x] Professional branding
- [x] Complete documentation
- [x] Testing and quality assurance

---

## 🏆 Summary

This is a comprehensive, professional Power BI dashboard suitable for:
- Sales performance analysis
- Team and category benchmarking
- Executive reporting
- Strategic decision-making
- Performance tracking

**Perfect for organizations needing actionable sales insights!**

---

**Made with Power BI | 2026 | ⭐ Star on GitHub if helpful!**
