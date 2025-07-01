# Texas Energy Burden Analysis (SQL + Tableau)

## Overview

This project analyzes energy burden across Texas ZIP Code Tabulation Areas (ZCTAs) to identify areas where energy costs disproportionately impact low-income households. Using SQL for data preparation and Tableau for visualization, this project provides clear, actionable insights for targeted energy equity interventions.

## Objectives

* Calculate average energy burden across Texas ZCTAs.
* Identify ZIP codes with above-average energy burden.
* Visualize high-burden areas using Tableau dashboards.
* Support data-driven decisions for equitable energy policy and planning.

## Dataset

* **Source:** Publicly available Texas energy burden and income data (2023).
* **Columns include:**

  * ZIP Code
  * Median Income
  * Energy Burden (%)
  * Margin of Error
  * Annual Energy Cost

## Tools Used

* SQL (SQLite/DB Browser): Data cleaning, filtering, aggregation, and band analysis.
* Tableau: Visualization of burden bands and geographic distribution.
* GitHub: Version control and portfolio presentation.

## Key SQL Processes

* Categorized ZIP codes into burden bands:

  * `<2%`
  * `2-3%`
  * `3-4%`
  * `>4%`
* Calculated:

  * Average energy burden
  * Average median income per band
  * ZIP code counts per band
* Prepared a funnel analysis for Tableau.

### Example SQL Snippet

```sql
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
```

## Visualizations

Tableau dashboards include:

* Funnel chart visualizing drop-offs across burden bands.
* Heat maps highlighting ZIP codes with the highest energy burdens.
* Bar charts showing average median income vs. burden bands.

Visuals will be added to `/images` upon publication.

## Key Insights

* The average energy burden across sampled Texas ZIP codes is 2.65%.
* ZIP codes with an energy burden over 4% have significantly lower median incomes, indicating a need for targeted support.
* Funnel analysis clarifies where energy relief programs may have the highest impact.

## Future Work

* Expand dataset to include all Texas ZCTAs.
* Join with ERCOT energy price data and weather data for deeper analysis.
* Build an interactive Tableau Public dashboard for stakeholders.

## About

I am Jonelle Wiley, a Data and Business Analyst focused on the energy and utilities sector. I leverage SQL, Tableau, and GIS mapping to translate complex data into actionable insights supporting equity and sustainability.

## Contact

* Email: [jonelle.wiley0210@gmail.com](mailto:jonelle.wiley0210@gmail.com)
* LinkedIn: linkedin.com/in/jonelle-wiley-4ba570127
