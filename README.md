 # :haus: King County Housing Price Prediction
## :reißzwecke: Overview
This project predicts **house sale prices** in **King County, Washington** (21,613 sales, 2014–2015).
We explored the data, identified key drivers of price, and tested multiple machine learning models.
**Goal:** Find the best model for accurate price prediction and understand which features matter most.
---
## :offener_ordner: Dataset
- **Target:** `price` (USD)
- **Features:** bedrooms, bathrooms, `sqft_living`, lot size, floors, `waterfront`, `view`, `condition`, `grade`, year built/renovated, `zipcode`, `lat`, `long`
---
## :zahnrad: Workflow
1. **Data Cleaning**: handled duplicates, converted dates, removed irrelevant columns.
2. **EDA**: histograms, boxplots, correlation heatmaps.
   - Top drivers: `sqft_living`, `grade`, `sqft_above`, `sqft_living15`.
   - For expensive homes (≥ $650k), **size** and **grade** matter most.
3. **Models Tested**:
   - KNN → poor generalization (R² ~0.25)
   - Linear Regression → decent baseline (R² ~0.70)
   - Random Forest → strong (R² ~0.89, RMSE ~114k)
   - XGBoost → best baseline (R² ~0.897, RMSE ~111k)
4. **Improvements**:
   - Dropping low-correlation features hurt performance.
   - Dropping low-importance features improved slightly (R² ~0.76).
   - **Hyperparameter tuning of XGBoost** → best result (R² ~0.908, RMSE ~109k).
---
## :balkendiagramm: Results
| Model              | RMSE (USD) | R²   |
|--------------------|------------|------|
| KNN                | ~300k      | 0.25 |
| Linear Regression  | 200–360k   | 0.70 |
| Random Forest      | 114k       | 0.89 |
| XGBoost (baseline) | 111k       | 0.897|
| **XGBoost (tuned)**| **109k**   | **0.908** |
**Key Insight:** Tree-based models (RF, XGBoost) dramatically outperform simpler baselines.
The tuned XGBoost is the final model, explaining ~91% of price variability.
