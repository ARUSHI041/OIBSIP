# EDA on Retail Sales Data: Bike Store

**Oasis Infobyte (OIBSIP) | Data Analytics | Level 1, Task 1**

## Objective
Perform an exploratory data analysis on a retail sales dataset to uncover sales trends, customer behaviour and product performance, and turn the findings into actionable business recommendations.

## Dataset
- **Source:** Kaggle, "Sales Data for Economic Data Analysis" (user abhishekrp1517)
- **Size:** 34,867 rows x 16 columns, bike store transactions from January 2015 to July 2016
- **Key columns:** Date, Customer Age, Customer Gender, Country, State, Product Category, Sub Category, Quantity, Unit Cost, Unit Price, Cost, Revenue

## Data preparation
- Dropped one empty row (only a Revenue value, no date or product).
- Dropped the `index` column (row number) and `Column1` (filled in only 7% of rows and unrelated to Revenue or Profit).
- Converted Date to datetime and Year, Customer Age and Quantity to integers.
- Created Profit (Revenue - Cost), Age Group, Year-Month and Quarter columns.
- Final dataset: 34,866 rows, no missing values, no duplicates.

## Analysis performed
1. Data inspection (shape, types, nulls, duplicates)
2. Descriptive statistics (mean, median, mode, standard deviation)
3. Time series analysis: monthly and quarterly revenue
4. Customer demographics: age groups and gender
5. Product analysis: top 10 products and revenue by category
6. Correlation heatmap and profit margin by sub category
7. Conclusions and recommendations

## Key findings
- **Data coverage matters.** January to June 2015 contains only Bikes; Accessories and Clothing appear from July 2015. The jump in revenue in 2015 Q3 therefore reflects broader product coverage, not real growth. July 2016 has no Bikes data.
- **Like-for-like growth** from 2015 Q4 onwards: about +8% in 2016 Q1 and about +23% in 2016 Q2 (quarter over quarter). December 2015 is the peak month.
- **Bikes earn 51% of revenue but only 15% of profit** (margin 2.9%). Accessories (18.6%) and Clothing (15.9%) have much healthier margins.
- **Helmets earned about 3.5x the profit of Mountain Bikes** on roughly half the revenue.
- Customers aged **25-44 make up about 62% of transactions**; 35-44 year olds spend the most per transaction. Gender split is almost even and does not affect spending.
- Revenue is strongly correlated with Cost (0.98) and Unit Price (0.85), and not with Quantity or Customer Age.

## Recommendations
1. Review Bikes pricing and supplier costs, since all three bike types earn margins below 4%.
2. Bundle high-margin accessories (helmets, gloves, bottles, tires) with bike sales.
3. Focus marketing on customers aged 25-44, and use entry-level offers for the 17-24 group.

## Visuals
![Monthly trend](monthly_trend.png)
![Revenue by category](monthly_revenue_by_category.png)
![Quarterly revenue](quarterly_revenue.png)
![Demographics](demographics.png)
![Product analysis](product_analysis.png)
![Correlation heatmap](correlation_heatmap.png)
![Margin by sub category](margin_by_subcategory.png)

## Limitations
- No customer ID, so counts are transactions, not unique customers.
- Product coverage differs by period, so totals across periods should be compared with caution.
- Profit is based on the dataset's Cost column, whose exact definition is not documented.

## Files
| File | Description |
|---|---|
| `retail_sales_eda.ipynb` | Full notebook with code, charts and written observations |
| `sales_data.csv` | Dataset |
| `*.png` | Charts used in this README |

## Tools
Python, pandas, NumPy, Matplotlib, Seaborn, Google Colab
