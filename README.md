# Zika Case Prediction

## Overview

The project follows a standard data mining workflow including data cleaning, exploratory data analysis (EDA), feature engineering, model training, validation, and Kaggle submission generation.

The problem is treated as a supervised machine learning regression problem because the target variable (`cases`) is numeric.

---

## Data Used

The following datasets were used in this project:

- `train.csv` — training dataset containing weekly Zika case counts
- `test.csv` — test dataset used for Kaggle predictions
- `weather.csv` — daily weather observations
- `dengue.csv` — dengue-related epidemiological data
- `sample_submission.csv` — Kaggle submission format template

---

## Data Cleaning

Several preprocessing and cleaning steps were performed:

- Converted epidemiological week and weather dates into datetime format
- Corrected inconsistent epidemiological week intervals
- Verified weekly spacing between epidemiological records
- Handled missing values using median imputation
- Aligned daily weather observations with epidemiological weeks using `merge_asof()`


---

## Exploratory Data Analysis

Exploratory analysis was conducted to better understand:

- distribution of Zika cases
- missing values
- variable relationships
- temporal trends
- feature correlations

The following visualisations were used:

- histograms
- boxplots
- line plots
- correlation heatmaps

---

## Feature Engineering

Several feature engineering steps were applied:

- aggregation of daily weather into weekly weather features
- merging weather data with epidemiological data
- merging dengue-related features
- creation of time-based features:
  - year
  - month
  - epidemiological week number

---

## Model Used

A Random Forest Regressor was used as the baseline machine learning model.

Reasons for choosing Random Forest:

- works well with tabular data
- handles non-linear relationships
- robust against overfitting
- supports feature importance analysis

---

## Validation / Kaggle Score

The dataset was split into training and validation sets using the holdout validation method.

Model performance was evaluated using:

- Mean Absolute Error (MAE)

---

## Final Submission

Predictions were generated for the Kaggle test dataset and exported in the required format:

ID_cases,cases
