# econ3916-midterm-project

# Schooling and Earnings Across U.S. States, 2022–2024

## Research question

How is estimated average schooling associated with median annual earnings across the 50 U.S. states, controlling for population size and median age?

## Data

I use the U.S. Census Bureau’s ACS 1-Year Estimates Detailed Tables for 2022, 2023 and 2024:

- B15003: educational attainment among adults aged 25+.
- B20004: median annual earnings among adults aged 25+ with earnings.
- B01003: total population.
- B01002: median age.

Source: https://data.census.gov/

The repository contains 12 original CSV files. After cleaning and merging, the dataset contains 150 state-year observations. DC and Puerto Rico are excluded.

I estimate average schooling years by assigning years to attainment categories and weighting them by population counts. The notebook documents these assignments.

## Method

I estimate separate OLS models for each year, comparing schooling-only models with models that additionally control for log population and median age. I use HC3 robust standard errors and examine residuals, Breusch–Pagan and Jarque–Bera tests, VIFs, and influential observations.

## How to run

1. Open the Colab notebook:
   https://colab.research.google.com/drive/127m-JJzKB1XmGt2Cij1kSByAM6MRh6hK?usp=sharing
2. Select Runtime → Run all.
3. The notebook reads the CSV files directly from this public repository. No manual upload is required.

The notebook produces the tables, figures, regression results and diagnostics used in the report. Its final “Numbers my report quotes” cell collects the reported numerical results.

## Main findings

Higher estimated average schooling is positively associated with median annual earnings in all three years.

In 2024, a 0.1-year higher estimated state average schooling level is associated with approximately $1,466 higher median annual earnings, controlling for population size and median age (95% CI: $1,114–$1,818; N = 50).

Excluding Utah, the most influential state in each year, changes the schooling coefficients by 3.00%–4.23% without reversing their direction. Utah remains in the main models.

These are state-level conditional associations, not causal effects or individual returns to schooling. Earnings are measured in each year’s dollars.

## Files

- `.csv` files: original ACS data.
- `.ipynb` file: analysis notebook with saved outputs.
- `.pdf` file: final written report and appendix.
