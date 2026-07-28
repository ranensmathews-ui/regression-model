# Hotazel Steam Regression Analysis

Regression analysis project examining the relationship between revenue and production, using monthly data with weather and seasonal variables.

## Data

Source file: `AICPA_regressionAnalysisData.csv`

Columns:
- `type` — data split label (`dt4training` or `dt4testing`)
- `date` — month-end date
- `revenue` — monthly revenue
- `production` — monthly production volume
- `coolDD` — cooling degree days
- `heatDD` — heating degree days

Data covers January 2011 through December 2014, split into a training set (2011–2013) and a testing set (2014).

## Feature Engineering

Two variables are added to the dataset:
- `winter_DV` — dummy variable equal to 1 if the month is December, January, or February, and 0 otherwise
- `winter_interaction` — interaction term calculated as `production * winter_DV`, used to test whether the effect of production on revenue differs in winter months

## Workflow

1. Load the CSV and parse `date` as a datetime column
2. Create the `winter_DV` and `winter_interaction` columns
3. Split the data into `dt4training` and `dt4testing` subsets based on the `type` column

## Libraries Used

- `numpy`
- `pandas`
- `matplotlib`
- `statsmodels`
