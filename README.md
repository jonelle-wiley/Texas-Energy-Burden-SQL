# Texas Energy Burden SQL Analysis

This project analyzes **energy burden across Texas counties** using census and utility data to identify areas where households spend a high percentage of income on energy costs. The analysis uses **SQL for data cleaning, preparation, and aggregation**, followed by visualization in Tableau to highlight disparities and support targeted energy efficiency and assistance programs.

## 📊 Project Goals
- Identify Texas counties with the highest energy burden rates.
- Visualize income-to-energy cost ratios for informed decision-making.
- Map disparities to support targeted interventions and policy discussions.

## 🛠️ Tools & Skills
- **SQL:** Data cleaning, joining, aggregation, exploratory queries.
- **Excel:** Data preparation, validation, and formatting.
- **Tableau:** Dashboard creation for visual insights.
- **GIS Mapping:** Spatial analysis to visualize energy burden distribution.

## 🧑‍💻 Code Highlights

### Example SQL Query:
```sql
SELECT 
    county,
    AVG(energy_cost) AS avg_energy_cost,
    AVG(income) AS avg_income,
    (AVG(energy_cost) / NULLIF(AVG(income), 0)) * 100 AS energy_burden_percentage
FROM 
    texas_energy_data
GROUP BY 
    county
ORDER BY 
    energy_burden_percentage DESC;
```

This query calculates the **average energy cost, income, and energy burden percentage** by county across Texas to identify areas with the highest energy burden.

## 🗂️ Files Included
- `energy_burden_cleaning.sql` – Data cleaning and preparation scripts.
- `energy_burden_analysis.sql` – Queries for insights and aggregations.
- `energy_burden_dashboard.twbx` – Tableau dashboard file.
- `data/` – Cleaned CSV files for reproducibility.

## 🚀 How to Use
1. Clone this repository to your local machine.
2. Run **SQL scripts** on your SQL environment for cleaning and analysis.
3. Open the Tableau dashboard for visual insights.
4. Adapt scripts and dashboards for additional energy or utilities analysis projects.

## 📫 Contact
**Jonelle Wiley** | Houston, TX | Remote  
🔗 [LinkedIn](https://www.linkedin.com/in/yourusername) | [Tableau Public](https://public.tableau.com/app/profile/yourusername)

✨ Feel free to use or adapt these scripts for your **energy analytics and sustainability projects**.
