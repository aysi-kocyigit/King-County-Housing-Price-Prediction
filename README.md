# King County Housing Price Prediction

This project analyzes housing sale prices in **King County (Seattle area)** between May 2014 and May 2015.  
The dataset includes **21,613 house sales** with 21 features related to house characteristics and location.  
The goal is to build and compare machine learning models to predict house prices and identify the most important features influencing them.

## Dataset
- Source: King County housing sales dataset (May 2014 – May 2015)
- Size: 21,613 rows, 21 features
- Target variable: `price`

## Objectives
1. Setup  
2. Initial Data Inspection  
3. Data Cleaning  
4. Exploratory Data Analysis (EDA)  
5. Machine Learning Models  
6. Improving Data  
7. Improving the XGBoost Model  
8. Conclusion  

## Methods
- **Data Cleaning:** Converted and extracted features from the `date` column, removed unnecessary columns, checked duplicates/missing values.  
- **EDA:** Visualized distributions, outliers, and correlations. Compared patterns between standard and expensive houses.  
- **Models Tested:**  
  - K-Nearest Neighbors (KNN)  
  - Linear Regression  
  - Random Forest Regressor  
  - XGBoost Regressor  
- **Model Comparison:** Evaluated models using RMSE and R² scores on train/test splits.  
- **Improvements:** Feature selection experiments and hyperparameter tuning of XGBoost.  

## Results
- **KNN:** Poor performance, high errors, overfitting.  
- **Linear Regression:** Reasonable baseline, explains ~70% variance, but limited for non-linear effects.  
- **Random Forest:** Strong performance (~89% R², RMSE ~114K on test).  
- **XGBoost (tuned):** Best model with **R² ≈ 0.91** and **RMSE ≈ 109K** on the test set.  

## Conclusion
- House size (`sqft_living`) and quality (`grade`) are the most influential features.  
- Outliers exist but tree-based models handle them effectively.  
- **Tuned XGBoost** provides the most accurate predictions.  
- Future improvements could include feature engineering (geographic clustering, external data) and testing other boosting algorithms.
