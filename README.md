# Prepare Early for Seasonal Salmonellosis Surges

## Using Weekly CDC Reports to Support Earlier Public Health Planning

**Authors:** Siwar, Abdallah, and Husam

## Business Problem

Health departments need time to prepare for increases in Salmonellosis cases. Understanding seasonal patterns and estimating future cases can support earlier decisions about testing, staffing, and public health communication.

This analysis answers five questions:

1. How have reported cases changed over time?
2. During which season do cases increase the most?
3. Which states have the highest reported rates compared with their population?
4. What should national planners expect over the next six months?
5. How accurately can cases be predicted one week ahead?

![Salmonellosis banner](visuals/salmonella-banner.jpg)

## Data

- **Source:** [CDC NNDSS Weekly Data](https://data.cdc.gov/NNDSS/NNDSS-Weekly-Data/x9gk-5huc/about_data)
- **Publisher:** Centers for Disease Control and Prevention
- **Disease:** Salmonellosis, excluding Typhi and Paratyphi infections
- **Time period:** 2022 to September 2026

The original data contains weekly reports for around 120 diseases. This analysis focuses only on Salmonellosis.

The data includes reported cases from U.S. states, territories, regions, and national summary areas.

Population estimates from the U.S. Census Bureau were also used to calculate state rates per 100,000 residents. This allows states with different population sizes to be compared more fairly.

## Methods

- Reviewed the CDC data flags to understand why some values were missing.
- Changed weeks marked as having no reported cases to zero.
- Standardized reporting-area names.
- Calculated state rates per 100,000 residents.
- Studied weekly, monthly, and seasonal patterns.
- Used a time-series model to forecast national monthly cases for six months.
- Used earlier weeks to train the machine-learning models.
- Used later weeks to test performance on unseen data.
- Compared Linear Regression, Random Forest, a tuned Random Forest, and a TensorFlow Neural Network.
- Compared every trained model with a simple baseline that uses the previous week’s cases as the next prediction.

## Results

### Weekly Reported Cases

![Weekly reported Salmonellosis cases](visuals/weekly_salmonellosis_cases.png)

> Reported cases change throughout the year instead of remaining at the same level. Repeated increases can be seen during warmer months, especially in 2026.

### Cases Are Highest in Summer

![Average weekly cases by season](visuals/salmonellosis_cases_by_season.png)

> Summer had the highest average, with approximately **650 reported cases per week**. Winter had the lowest average, with approximately **247 cases per week**.

The seasonal pattern reached its highest point around **week 34**, which is usually in August.

The monthly analysis also found that **August** had the highest number of cases, while **February** had the lowest.

### States With the Highest Reported Rates

![States with the highest Salmonellosis rates](visuals/highest_salmonellosis_rates.png)

> Mississippi had the highest year-to-date reported rate, with **26.8 cases per 100,000 residents** through week 35 of 2026.



## Recommendations

- Prepare additional testing and public health resources before the summer increase.
- Pay closer attention to weekly reports during August and around week 34.
- Use population-adjusted rates when deciding which states may need more support.
- Compare new cases with the normal seasonal level before treating an increase as a possible outbreak.
- Use the previous-week baseline for short-term predictions until a trained model clearly performs better.
- Use the six-month national forecast to support longer-term resource planning.
- Review missing values and reporting delays before making important decisions.

## Limitations

- The data contains reported cases, which may be lower than the true number of infections.
- Reporting practices and delays may differ between states.
- The latest year is incomplete, so it should not be compared directly with a full year.
- The state-rate analysis uses 2024 population estimates with 2026 case reports.
- A normal seasonal increase does not always mean an unusual outbreak is happening.
- The six-month forecast uses national monthly totals, so it shows a general direction rather than a weekly prediction.
- The short-term analysis includes states, territories, regions, and national summary areas with very different case levels.
- Large reporting areas may have a stronger effect on the overall performance results.
- The Neural Network was the best trained model, but it did not beat the previous-week baseline.

## Next Steps

- Repeat the short-term analysis using states only.
- Check prediction errors separately for each state.
- Test information from several previous weeks instead of using only one week.
- Add features that show whether cases are increasing or decreasing.
- Create a clear rule for identifying unusually high weeks.
- Keep the previous-week baseline as a benchmark when testing new models.
- Compare the six-month forecast with actual cases as new CDC reports become available.
- Update the analysis when new CDC data becomes available.

## For Further Information

- [CDC NNDSS Weekly Data](https://data.cdc.gov/NNDSS/NNDSS-Weekly-Data/x9gk-5huc/about_data)
- [Data preparation notebook](notebooks/01_preparing_data.ipynb)
- [Salmonellosis analysis notebook](notebooks/02_salmonellosis_analysis.ipynb)
- [Salmonellosis forecasting notebook](notebooks/03_salmonellosis_forecasting.ipynb)
- [Machine-learning and deep-learning notebook](notebooks/04_salmonellosis_ml.ipynb)

For additional questions, please contact [Siwar Ehwass](mailto:siwarehwass@gmail.com).
