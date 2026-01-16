# Airline Ticket Price Prediction

**Course:** STAT 425 – Statistical Modeling I 
**Instructor:** Douglas Simpson 
**Semester:** Fall 2025
**Author:** Ting Yun Chen (tingyun3)

---

## Project Overview
This repository contains my STAT 425 graduate final project on modeling airline ticket prices.
Using a large-scale flight dataset (~300,000 observations), the project applies regression-based
modeling to predict ticket prices and to identify which flight characteristics and booking factors
most strongly explain fare variation.

The analysis is written as a single Quarto (.qmd) report that integrates data cleaning, modeling,
diagnostics, and interpretation into a reproducible workflow.

## Dataset
This project uses the public Flight Price Prediction dataset (Easemytrip / Kaggle) with flights
between major Indian metropolitan cities. The cleaned dataset contains 300,153 observations
and 11 variables after removing an index column.

## Methods
Models and analyses implemented in R include:
* Multiple Linear Regression (ANCOVA with categorical predictors and continuous covariates)
* Diagnostics: residual plots and multicollinearity assessment (GVIF/VIF)
* Nonlinear specification using B-splines (df = 4) for duration and booking lead time (days_left)
* Regularization using glmnet:
  - Lasso (alpha = 1) and Ridge (alpha = 0)
  - 5-fold cross-validation with RMSE as the primary metric
* Group comparisons via one-way and two-way ANOVA (including airline × class interaction)
* Linear mixed-effects model with random intercepts for airline and for route (source_city:destination_city)

## Selected Results
* The baseline OLS model achieves R^2 around 0.91.
* Adding spline terms improves fit (R^2 increases to ~0.915).
* In cross-validation, Lasso achieves lower RMSE (~6195) than Ridge (~6512), indicating that
  variable selection is beneficial in this high-dimensional dummy-variable setting.
* Across models, cabin class and booking lead time are dominant predictors of price.

## Repository Contents
- `airline_price_analysis.qmd`: Full reproducible analysis (code + discussion)
- `airline_price_analysis.pdf`: Rendered final report
- `data/README.md`: Data description and variable definitions
- `figures/`: Generated plots (if applicable)

## Tools and Technologies
**Programming Language:** R
**Libraries:** tidyverse, car, splines, glmnet, lme4, broom, doParallel
**Reporting:** Quarto

## Notes
This repository documents the final project only. Course homework assignments are not included.