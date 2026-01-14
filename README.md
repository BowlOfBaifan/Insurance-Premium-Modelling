# Insurance Price Predictor

A machine learning project predicting US health insurance charges using demographic and lifestyle factors.

## Overview

This project analyzes a dataset of 1,338 US health insurance records to predict individual medical costs. Through exploratory data analysis and feature engineering, we identify key cost drivers and build predictive models.

## Dataset

The dataset contains 7 features:
- age: Age of the insured
- sex: Gender (male/female)
- bmi: Body mass index
- children: Number of dependents
- smoker: Smoking status (yes/no)
- region: US geographic region (northeast, northwest, southeast, southwest)
- charges: Medical insurance costs (target variable)

## Key Findings

From EDA:
- Smoking status is the dominant predictor of charges (Cohen's d = 2.57)
- BMI has strong interaction with smoking: correlation with charges is 0.806 for smokers vs 0.084 for non-smokers
- Age shows moderate positive correlation (r = 0.299)
- Region and sex have minimal practical significance

## Models

### Linear Regression (Best Model)
- Features: age, bmi, children, smoker, sex, region, obese_smoker interaction, bmi_smoker interaction
- Mean CV R²: 0.863
- Mean CV RMSE: $4,422

### Random Forest
- Mean CV R²: 0.837
- Mean CV RMSE: $4,853

## Project Structure

```
├── EDA.ipynb           # Exploratory data analysis
├── modeling.ipynb      # Model building and evaluation
├── insurance.csv       # Dataset
└── README.md
```

## Requirements

- pandas
- numpy
- matplotlib
- plotly
- seaborn
- scikit-learn
- scipy
- statsmodels

## Usage

1. Run EDA.ipynb for data exploration and visualization
2. Run modeling.ipynb to train and evaluate models

## Limitations

The model systematically underpredicts charges for high-cost non-smokers. Additional features such as chronic conditions, medical history, and medications would improve predictions for this subgroup.
