Texas Energy Burden Analysis (SQL + Tableau)
Overview
This project analyzes energy burden across Texas ZIP Code Tabulation Areas (ZCTAs) to identify areas where energy costs disproportionately impact low-income households. Using SQL for data preparation and Tableau for visualization, the project delivers clear, actionable insights to support equitable energy policy and resource allocation.

Objectives
Calculate average energy burden across Texas ZCTAs.

Identify ZIP codes with above-average energy burdens.

Visualize high-burden areas using Tableau dashboards.

Support data-driven decisions for equitable energy planning.

Dataset
Source: Public Texas energy burden and income data (2023).

Columns:

ZIP Code

Median Income

Energy Burden (%)

Margin of Error

Annual Energy Cost

Tools Used
SQL (SQLite/DB Browser): Data cleaning, filtering, aggregation, and band analysis.

Tableau: Visualization of burden bands and geographic distribution.

Excel: Quick chart generation from SQL outputs.

GitHub: Version control and project presentation.

Key SQL Processes
Categorized ZIP codes into energy burden bands:

<2%

2-3%

3-4%

>4%

Calculated:

Average energy burden

Average median income per band

ZIP code counts per band

Example SQL Snippet
sql
Copy
Edit
SELECT
    CASE
        WHEN field5 < 2 THEN '<2% Burden'
        WHEN field5 >= 2 AND field5 < 3 THEN '2%-3% Burden'
        WHEN field5 >= 3 AND field5 < 4 THEN '3%-4% Burden'
        WHEN field5 >= 4 THEN '>4% Burden'
    END AS "Energy Burden Band",
    COUNT(*) AS "ZIP Code Count",
    ROUND(AVG(field2), 0) AS "Average Median Income"
FROM "Energy_Burden_Texas_ZIPCodes_2023"
GROUP BY "Energy Burden Band"
ORDER BY "ZIP Code Count" DESC;
Visualizations
Tableau dashboards include:

KPI cards summarizing average median income, average energy burden, and margin of error.

Heat maps highlighting ZIP codes with the highest energy burdens.

Bar charts showing average median income vs. burden bands.

Scatter plots illustrating the inverse relationship between income and energy burden.

Excel Output:

![Average Median Income by Energy Burden Band](screenshots/average_median_income_by_burden_band.png)

This chart demonstrates that ZIP codes with lower energy burdens generally have higher median incomes, underscoring the relationship between income and energy affordability.

Key Insights
✅ The average energy burden across sampled Texas ZIP codes is 2.89%.
✅ ZIP codes with >4% burden have significantly lower median incomes, indicating need for targeted support.
✅ Visual analyses clarify where energy relief programs can have the highest community impact.

Future Enhancements
Incorporate full Texas ZCTA dataset for statewide mapping.

Join with ERCOT energy price and weather data for predictive modeling.

Build interactive Tableau dashboards for stakeholder reporting.

About Me
I am Jonelle Wiley, a Data and Business Intelligence Analyst specializing in the energy and utilities sector. I leverage SQL, Tableau, and GIS mapping to translate complex datasets into actionable insights that drive equitable, data-informed decisions.

Contact
📧 jonelle.wiley0210@gmail.com
🔗 LinkedIn
