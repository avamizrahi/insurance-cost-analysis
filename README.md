# Medical Insurance Cost Drivers & Regression Modeling

## Overview
Multiple linear regression analysis identifying key predictors of medical
insurance charges using a 1,338-person dataset. Includes full model
diagnostics, outlier detection, model comparison, and multicollinearity
checks.

## Data
- Kaggle insurance dataset (auto-downloaded via script from GitHub)
- 1,338 observations, 7 variables: age, sex, BMI, children, smoker,
  region, charges
- No missing values; character variables converted to factors

## Methods
- Exploratory data analysis with ggplot2 visualizations
- Multiple linear regression with all predictors
- Residual diagnostics (Residuals vs Fitted, Q-Q, Scale-Location,
  Cook's Distance)
- Outlier detection using studentized residuals (|r| > 3) and
  Cook's Distance
- Model comparison: full model vs cleaned model (outliers removed)
- Stepwise AIC model selection (bidirectional)
- Multicollinearity check using VIF
- 95% confidence and prediction intervals for new observations

## Key Findings
| Metric | Full Model | Cleaned Model |
|---|---|---|
| Adjusted R² | 0.749 | 0.847 |
| RSE | $6,062 | $4,496 |
| AIC | 27,116 | 24,604 |

- Smoking status is by far the strongest predictor (+$24,796/year)
- Age and BMI are significant positive predictors
- Sex and region have minimal effect on charges
- All VIF values below 2 — no multicollinearity concerns
- Cleaned model predicts ~$6,411 for a 40-year-old non-smoking
  female with BMI 25, 2 children, northwest region

## Tools & Libraries
R, RMarkdown, ggplot2, tidyverse, dplyr
