# Healthcare Analytics for Doctor Visits

## Overview
This project analyses survey data from **5,190 people** to understand what influences how often they visit a doctor in a two-week period. It uses exploratory data analysis (EDA) in Python to find patterns linked to doctor visits.

**Core question:** Why do some people visit a doctor more often than others?

## Problem Statement
Some people visit a doctor many times, while most never visit at all. Healthcare providers need to know who visits doctors, how often, and why. Without this understanding, it is hard to plan capacity or to support the people with the greatest need.

## Objectives
- Describe how doctor visits are distributed across the population.
- Compare visits with age, gender, income, illness, health condition, chronic conditions and insurance cover.
- Identify the factors most strongly related to visits.
- Profile the "high users" (people with 2 or more visits).

## Dataset
- **Rows:** 5,190 | **Columns:** 12 | **Missing values:** none
- **Target variable:** `visits`

| Column | Description |
|---|---|
| visits | Doctor visits in the past 2 weeks (0 to 9) |
| gender | Male or female |
| age | Age divided by 100 |
| income | Annual income in A$10,000s |
| illness | Number of illnesses in the past 2 weeks (0 to 5) |
| reduced | Days of reduced activity due to illness (0 to 14) |
| health | General health score (higher = worse) |
| private | Has private health insurance |
| freepoor | Free government cover (low income) |
| freerepat | Free government cover (repatriation) |
| nchronic | Chronic condition without activity limitation |
| lchronic | Chronic condition with activity limitation |

**Data note:** 1,320 duplicate rows (25.4%) were found and **kept**. This is survey data, so different respondents can give identical answers. Removing them would bias the results (mean visits would rise from 0.30 to 0.39).

## Technology Used
- Python
- Jupyter Notebook / Google Colab
- Pandas, NumPy (data handling)
- Matplotlib, Seaborn (visualization)

## Project Workflow
1. Import libraries and load the data
2. Data inspection and cleaning (shape, info, nulls, duplicates)
3. Univariate analysis (gender, age, visits)
4. Bivariate analysis (visits against each factor)
5. Multivariate analysis (gender by chronic condition, correlation heatmap, high users)
6. Findings and conclusion

## How to Run
1. Install the libraries:
```
   pip install pandas numpy matplotlib seaborn jupyter
```
2. Place the CSV file and the notebook in the same folder.
3. Open the notebook:
```
   jupyter notebook Healthcare_Analytics_for_Doctor_Visits.ipynb
```
4. Update the file path in the data-loading cell if needed (in Colab: `/content/<file name>.csv`).
5. Run all cells in order.

## Key Findings
- **79.8%** of people had no doctor visit. The 5% with 2 or more visits account for about half of all visits.
- **Reduced-activity days** have the strongest link to visits (correlation 0.42), followed by illness (0.22) and health score (0.19).
- A **limiting chronic condition** more than doubles visits (0.60 vs 0.26).
- **Women** visit more than men (0.36 vs 0.24), and **seniors** visit about 2.2 times as often as the young.
- **Lower-income** groups visit more (0.40 vs 0.22 for the highest income group).
- **Private insurance** makes almost no difference (0.295 vs 0.307).

## Conclusion
Health need is the main factor influencing doctor visits. Reduced-activity days, number of illnesses, health score and limiting chronic conditions have the strongest relationship with healthcare use. Women, older people and lower-income groups visit more, partly because they report more illness. Planning should give more attention to people with limiting chronic conditions and frequent reduced-activity days, while also considering older and lower-income populations.

