# IT Expenditure Analysis – Power BI Dashboard

## 1. Project Overview

The IT Expenditure Analysis project focuses on analysing an organization's IT spending and identifying differences between actual expenditure, planned budgets and forecast budgets.

The objective is to understand expenditure patterns across different business areas, countries, regions, IT areas and cost elements to support better financial planning and cost management.

## 2. Business Problem

The organization faces challenges in managing IT expenditure due to significant variations between actual spending, planned budgets and forecast budgets.

This project aims to identify where expenditure differences occur and provide insights that can support better financial control and future budget planning.

## 3. Project Objectives

- Analyse actual IT expenditure against planned and forecast budgets.
- Identify monthly expenditure trends.
- Compare IT expenditure across business areas and countries.
- Identify regions with the highest IT spending.
- Analyse expenditure by IT area and IT sub-area.
- Identify major cost elements contributing to IT expenditure.
- Develop insights to support financial decision-making.

## 4. Dataset Description

**Dataset:** IT Expenditure Dataset.xlsx

**Source:** Course-provided dataset.

The analysis uses the `Data` sheet, containing 81,610 original records and 12 columns.

### Dataset Columns

| Column | Description |
|---|---|
| Date | Month of expenditure |
| Business Area | Business unit or functional area |
| Region | Geographical region |
| Country | Country associated with expenditure |
| IT Sub Area | Specific IT sub-area |
| IT Area | Main IT functional area |
| Cost element name | Name of the cost element |
| Cost Element Group | Main cost category |
| Cost Element Sub Group | Detailed cost category |
| Actual | Actual expenditure |
| Forecast | Forecast expenditure |
| Plan | Planned expenditure |

## 5. Tools and Technologies

- **Microsoft Power BI** – Dashboard development and visualization.
- **Power Query** – Data cleaning and transformation.
- **DAX** – Measures and calculations.
- **Microsoft Excel** – Source dataset.

## 6. Data Cleaning and Preparation

Data preparation was performed using Power Query.

The following steps were carried out:

- Checked and assigned appropriate data types.
- Applied Trim transformation to text columns.
- Replaced null values in numerical columns with zero as a working assumption.
- Checked column quality and data distribution.
- Investigated duplicate records.
- Retained the original 81,610 records for the main analysis because identical records could represent legitimate transactions without a unique transaction identifier.

**Note:** The impact of duplicate removal was compared before deciding to retain the original records.

## 7. DAX Measures

The following measures were created to calculate expenditure and budget differences.

### Total Actual
```dax
Total Actual = SUM('Data'[Actual])
```

### Total Plan
```dax
Total Plan = SUM('Data'[Plan])
```

### Total Forecast
```dax
Total Forecast = SUM('Data'[Forecast])
```

### Plan Variance
```dax
Plan Variance =
[Total Actual] - [Total Plan]
```

### Forecast Variance
```dax
Forecast Variance =
[Total Actual] - [Total Forecast]
```

### Plan Variance %
```dax
Plan Variance % =
DIVIDE([Plan Variance], [Total Plan], 0)
```

### Forecast Variance %
```dax
Forecast Variance % =
DIVIDE([Forecast Variance], [Total Forecast], 0)
```

## 8. Dashboard Visualizations

The Power BI dashboard includes:

1. KPI Cards – Total Actual, Total Plan, Total Forecast and variance measures.
2. Monthly IT Expenditure – Actual vs Plan vs Forecast.
3. Actual IT Expenditure by Business Area.
4. Actual IT Expenditure by Country.
5. Actual IT Expenditure by Region.
6. Actual IT Expenditure by IT Area.
7. Actual IT Expenditure by IT Sub Area.
8. Actual IT Expenditure by Cost Element Group.
9. Actual IT Expenditure by Cost Element Sub Group.

Interactive slicers are planned for Month, Country, Region, Business Area and IT Area.

## 9. Preliminary Findings

Based on the current dashboard:

- Total Actual Expenditure: **555.73M**
- Total Planned Expenditure: **900.40M**
- Total Forecast Expenditure: **890.54M**
- Plan Variance: **-344.67M**
- Forecast Variance: **-334.81M**
- Plan Variance Percentage: **-38.28%**
- Forecast Variance Percentage: **-37.60%**

Additional observations:

- Infrastructure is the highest-spending business area.
- USA accounts for the largest share of expenditure by country and region.
- Functional is the highest-spending IT area.
- Labor is the largest cost element group.
- External Labor and Internal Labor are major cost element sub-groups.

## 10. Important Data Limitation

The analysis uses only the `Data` sheet.

Actual expenditure is available for January to August, while September to December actual expenditure is stored in the separate `Future Data` sheet and is not included in this analysis.

Therefore, zero actual values from September to December in the current monthly chart should not be interpreted as confirmed zero expenditure.

The analysis should be treated as a partial-year actual expenditure analysis.

## 11. Conclusion

This project demonstrates how Power BI can be used to analyse IT expenditure, compare actual spending against budgets, identify major spending categories and explore expenditure patterns across different business dimensions.

The dashboard provides a foundation for understanding budget variances and identifying areas that may require further investigation to improve financial control and budget management.
