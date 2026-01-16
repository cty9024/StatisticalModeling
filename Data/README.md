# Data Description

## Source
This project uses the public "Flight Price Prediction" dataset released on Kaggle by the Easemytrip team.
The data contain flights between major Indian metropolitan cities and are commonly used for airfare
prediction tasks.

## File
`Clean_Dataset.csv`

## Observations and Cleaning
The cleaned dataset used in the analysis contains 300,153 rows and 11 variables.
The original CSV includes an unnamed index column (`...1`), which is removed prior to modeling.
No missing values are present in the dataset, so no imputation is performed.
Categorical variables are converted to factors in R.

## Unit of Observation
Each row represents a scheduled commercial flight with associated booking and schedule characteristics.
The response variable is ticket price in INR.

## Variables
Target (Response):
- price (numeric): ticket price in INR

## Predictors (Features):
Categorical:
- airline: airline carrier (e.g., Air_India, Indigo, Vistara, etc.)
- flight: flight code (alphanumeric)
- source_city: departure city (six major metro cities)
- destination_city: arrival city (six major metro cities)
- class: cabin class (Business, Economy)
- stops: number of stops (zero, one, two_or_more)
- departure_time: departure time-of-day bin (Early_Morning, Morning, Afternoon, Evening, Night, Late_Night)
- arrival_time: arrival time-of-day bin (Early_Morning, Morning, Afternoon, Evening, Night, Late_Night)

## Continuous:
- duration (numeric): flight duration in hours
- days_left (numeric): number of days between booking date and departure date (booking lead time)

## Notes for Reproducibility
- If the raw CSV is not committed to this repository, download the dataset from Kaggle and place
  `Clean_Dataset.csv` under the `data/` folder (or update the file path in the .qmd).
- The modeling code expects the index column to be removed and categorical variables to be treated as factors.
