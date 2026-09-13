# DAX Queries & Measures

Complete collection of 50+ DAX measures for Amazon Sales Dashboard. Copy and paste directly into Power BI.

---

## 1. Basic KPI Measures

**Total Sales**
```dax
SUM('amazon_sales_dataset_2019_2024_'[Total Sales])
```

**Total Orders**
```dax
COUNTROWS('amazon_sales_dataset_2019_2024_')
```

**Total Profit**
```dax
SUM('amazon_sales_dataset_2019_2024_'[Profit Margin])
```

**Avg Order Value**
```dax
DIVIDE([Total Sales],[Total Orders],0)
```

**Total Customers**
```dax
DISTINCTCOUNT('amazon_sales_dataset_2019_2024_'[Customer ID])
```

**Avg Profit Margin**
```dax
AVERAGE('amazon_sales_dataset_2019_2024_'[Profit Margin])
```

---

## 2. Order Status Analysis

**Completed Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Order Status]="Completed")
```

**Pending Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Order Status]="Pending")
```

**Cancelled Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Order Status]="Cancelled")
```

**Returned Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Order Status]="Returned")
```

**Completion Rate %**
```dax
DIVIDE([Completed Orders],[Total Orders],0)*100
```

**Return Rate %**
```dax
DIVIDE([Returned Orders],[Total Orders],0)*100
```

**Cancellation Rate %**
```dax
DIVIDE([Cancelled Orders],[Total Orders],0)*100
```

---

## 3. Sales by Dimension

**Sales by Region**
```dax
CALCULATE([Total Sales],'amazon_sales_dataset_2019_2024_'[Region])
```

**Sales by Category**
```dax
CALCULATE([Total Sales],'amazon_sales_dataset_2019_2024_'[Product Category])
```

**Sales by Salesperson**
```dax
CALCULATE([Total Sales],'amazon_sales_dataset_2019_2024_'[Salesperson])
```

**Sales by Payment Method**
```dax
CALCULATE([Total Sales],'amazon_sales_dataset_2019_2024_'[Payment Method])
```

**Sales by Order Status**
```dax
CALCULATE([Total Sales],'amazon_sales_dataset_2019_2024_'[Order Status])
```

---

## 4. Counts & Distinctness

**Total Products**
```dax
DISTINCTCOUNT('amazon_sales_dataset_2019_2024_'[Product Name])
```

**Total Categories**
```dax
DISTINCTCOUNT('amazon_sales_dataset_2019_2024_'[Product Category])
```

**Total Regions**
```dax
DISTINCTCOUNT('amazon_sales_dataset_2019_2024_'[Region])
```

**Total Salespeople**
```dax
DISTINCTCOUNT('amazon_sales_dataset_2019_2024_'[Salesperson])
```

**Total Quantity Sold**
```dax
SUM('amazon_sales_dataset_2019_2024_'[Quantity Sold])
```

---

## 5. Averages & Aggregations

**Average Discount**
```dax
AVERAGE('amazon_sales_dataset_2019_2024_'[Discount (%)])
```

**Average Unit Price**
```dax
AVERAGE('amazon_sales_dataset_2019_2024_'[Unit Price])
```

**Max Unit Price**
```dax
MAX('amazon_sales_dataset_2019_2024_'[Unit Price])
```

**Min Unit Price**
```dax
MIN('amazon_sales_dataset_2019_2024_'[Unit Price])
```

**Avg Quantity per Order**
```dax
DIVIDE([Total Quantity Sold],[Total Orders],0)
```

---

## 6. Profitability Analysis

**Profit Margin %**
```dax
DIVIDE([Total Profit],[Total Sales],0)*100
```

**Profit to Sales Ratio**
```dax
[Total Profit]/[Total Sales]
```

**Total Discount Amount**
```dax
SUMX('amazon_sales_dataset_2019_2024_',('amazon_sales_dataset_2019_2024_'[Unit Price]*'amazon_sales_dataset_2019_2024_'[Quantity Sold]*'amazon_sales_dataset_2019_2024_'[Discount (%)]/100))
```

**Effective Selling Price**
```dax
DIVIDE([Total Sales],[Total Quantity Sold],0)
```

---

## 7. Ranking & Top Performers

**Top Salesperson**
```dax
MINX(FILTER(ALL('amazon_sales_dataset_2019_2024_'[Salesperson]),[Sales by Salesperson]=MAXX(ALL('amazon_sales_dataset_2019_2024_'[Salesperson]),[Sales by Salesperson])),'amazon_sales_dataset_2019_2024_'[Salesperson])
```

**Top Category Name**
```dax
MAXX(TOPN(1,VALUES('amazon_sales_dataset_2019_2024_'[Product Category]),[Total Sales]),'amazon_sales_dataset_2019_2024_'[Product Category])
```

**Rank by Sales**
```dax
RANKX(ALL('amazon_sales_dataset_2019_2024_'[Salesperson]),CALCULATE([Total Sales]),,DESC)
```

---

## 8. Time-Based Measures

**Year**
```dax
YEAR('amazon_sales_dataset_2019_2024_'[Order Date])
```

**Month**
```dax
MONTH('amazon_sales_dataset_2019_2024_'[Order Date])
```

**Month Name**
```dax
FORMAT('amazon_sales_dataset_2019_2024_'[Order Date],"mmmm")
```

**Quarter**
```dax
"Q"&ROUNDUP(MONTH('amazon_sales_dataset_2019_2024_'[Order Date])/3,0)
```

**Sales MTD (Month-to-Date)**
```dax
CALCULATE([Total Sales],DATESMTD('amazon_sales_dataset_2019_2024_'[Order Date]))
```

**Sales YTD (Year-to-Date)**
```dax
CALCULATE([Total Sales],DATESYTD('amazon_sales_dataset_2019_2024_'[Order Date]))
```

---

## 9. Year-over-Year Analysis

**Prior Year Sales**
```dax
CALCULATE([Total Sales],SAMEPERIODLASTYEAR('amazon_sales_dataset_2019_2024_'[Order Date]))
```

**YoY Growth %**
```dax
VAR CurrentYear=[Total Sales] VAR PriorYear=[Prior Year Sales] RETURN DIVIDE(CurrentYear-PriorYear,PriorYear,0)*100
```

**MoM Growth %**
```dax
VAR CurrentMonth=[Total Sales] VAR PriorMonth=CALCULATE([Total Sales],DATEADD('amazon_sales_dataset_2019_2024_'[Order Date],-1,MONTH)) RETURN DIVIDE(CurrentMonth-PriorMonth,PriorMonth,0)*100
```

---

## 10. Conditional Measures

**High Value Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Total Sales]>[Avg Order Value])
```

**Discounted Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Discount (%)]>0)
```

**High Discount Orders (>15%)**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Discount (%)>=15])
```

**Profitable Orders**
```dax
CALCULATE([Total Orders],'amazon_sales_dataset_2019_2024_'[Profit Margin]>0)
```

---

## 11. Advanced Calculations

**Running Total Sales**
```dax
CALCULATE([Total Sales],FILTER(ALL('amazon_sales_dataset_2019_2024_'[Order Date]),'amazon_sales_dataset_2019_2024_'[Order Date]<=MAX('amazon_sales_dataset_2019_2024_'[Order Date])))
```

**Sales Performance vs Target**
```dax
VAR Target = 1000000 RETURN DIVIDE([Total Sales],Target,0)*100
```

**Category Performance Index**
```dax
DIVIDE([Sales by Category],CALCULATE([Total Sales],ALL('amazon_sales_dataset_2019_2024_'[Product Category])),0)
```

**Salesperson Efficiency**
```dax
DIVIDE([Total Sales],[Total Orders],0)
```

---

## Usage Instructions

1. **Copy the formula** from the section above
2. **Open Power BI Desktop**
3. **Go to Modeling tab**
4. **Click "New Measure"**
5. **Paste the formula**
6. **Replace table name** if different (currently: `'amazon_sales_dataset_2019_2024_'`)
7. **Click checkmark** to save
8. **Use in visualizations**

---

## Formula Naming Convention

All formulas use the table name:
```
'amazon_sales_dataset_2019_2024_'
```

If your table has a different name, replace it in all formulas.

**Example:**
```
Original:  SUM('amazon_sales_dataset_2019_2024_'[Total Sales])
Modified:  SUM('YourTableName'[Total Sales])
```

---

## Common Errors & Solutions

| Error | Solution |
|-------|----------|
| "Table not found" | Update table name in formula |
| "Column not found" | Check exact column name spelling |
| "Circular reference" | Remove self-referencing measures |
| "Unexpected token" | Ensure proper syntax and brackets |

---

## Quick Reference

**Most Used Measures:**
- Total Sales - Revenue metric
- Total Orders - Volume metric
- Profit Margin % - Profitability
- Completion Rate % - Operational health
- Sales by Category - Category performance
- Rank by Sales - Team performance

---

**Total Measures:** 50+  
**Last Updated:** September 2026  
**Status:** Production Ready ✅

---

**Tip:** Use these measures in combination with slicers for dynamic analysis!
