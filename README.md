# Bike Buyers: Predicting Purchase Interest

**Author:** Suryansh Mishra · [GitHub](https://github.com/Suryansh2111) · co-authored with Pranjal Shandilya ([pranjalshandilya](https://github.com/pranjalshandilya))

## Problem

A bike showroom wants to understand customer demographics in its area and add a first-pass filter to its website's interest form. Predicting who is likely to buy lets the showroom prioritize appointments with the most promising prospects.

## Data

Kaggle Bike Buyers dataset: 1,000 customers with marital status, gender, income, children, education, occupation, home ownership, cars, commute distance, region and age. Target: `Purchased.Bike` (yes/no).

## Approach

- Univariate, bivariate and multivariate EDA, testing 8 hypotheses about who buys (for example, people with no car who live nearby).
- Missing values filled with kNN imputation (VIM package in R); cleaned data in `bike_buyers_imputed.csv`.
- Dummy variables for categoricals, ordinal mapping for education and commute distance.
- Models: k-Nearest Neighbors (k = 5) and a Decision Tree (Gini, max depth 10).

## Results (test set, 250 customers)

| Model | Accuracy | F1 (buyers) |
| --- | --- | --- |
| Decision Tree | **66%** | 0.63 |
| kNN (k = 5) | 60% | 0.61 |

## Key findings

- Single customers convert more often than married ones (about 54% vs 42%).
- Customers with no car, or one car, are the most likely buyers; interest falls with more cars.
- Commutes of 2-5 miles convert best; 10+ miles convert least.
- Professionals buy most; management least.

## Files

- `ML_BikeBuyers.ipynb`: analysis and models
- `bike_buyers_imputed.csv`: cleaned data

**Tools:** Python, pandas, scikit-learn, seaborn, R (VIM)
