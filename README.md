# Home_Price
**code file** -  https://github.com/323kZ/home_price/blob/main/home_data.ipynb
**ppt of the complete project** - https://github.com/323kZ/home_price/blob/main/price.pptx
## Overview

This project focuses on building a predictive data science model to analyze how various factors influence US home prices over the last 20 years. The S&P CoreLogic Case-Shiller U.S. National Home Price Index (CSUSHPISA) is used as the target variable for home prices.

---

## Project Structure

The workflow is organized into the following stages:

1. **Data Collection**

   - **Datasets Used:**
     - [S&P CoreLogic Case-Shiller U.S. National Home Price Index](https://fred.stlouisfed.org/series/CSUSHPISA)
     - [Redfin Market Tracker Dataset](https://redfin-public-data.s3.us-west-2.amazonaws.com/redfin_market_tracker/us_national_market_tracker.tsv000.gz)

2. **Data Preprocessing**

   - Steps include:
     - Parsing and aligning date columns.
     - Merging datasets based on date fields.
     - Handling missing values and rounding numeric features.

3. **Exploratory Data Analysis (EDA)**

   - Visualizations include:
     - Correlation heatmaps.
     - Pairwise scatterplots.
     - Time-series trends and boxplots.
     - Regression plots for key features.

4. **Feature Engineering**

   - Creation of lagged, seasonal, and derived metrics.
   - Log transformations for skewed features.
   - Dropping NA values after feature generation.

5. **Feature Selection**

   - Techniques include:
     - Correlation analysis.
     - Random Forest feature importance.
     - Variance Inflation Factor (VIF) analysis to address multicollinearity.
   - Features were scaled using `StandardScaler`.

6. **Model Development and Evaluation**

   - **Base Models Tested:**
     - Linear Regression
     - Decision Tree Regressor
     - Random Forest Regressor
     - XGBoost Regressor
   - Evaluation metrics include:
     - R²
     - Mean Absolute Error (MAE)
     - Root Mean Squared Error (RMSE)

7. **Hyperparameter Tuning**

   - Performed on Random Forest using `GridSearchCV`.
   - Best parameters were identified and implemented to optimize performance.

---

## Key Insights

- **Best Model:** Random Forest Regressor

  - **Metrics (after tuning):**
    - R²: \~0.95
    - MAE: Low
    - RMSE: Low

- **Significant Features:**

  - Lagged sale prices (1, 3, 6 months).
  - Median sale price.
  - Median price per square foot (PPSF).
  - Inventory-to-sales ratio.
  - Seasonal adjustments.

---

## Required Dependencies

- Python Libraries:
  - pandas
  - numpy
  - seaborn
  - matplotlib
  - sklearn
  - xgboost
  - statsmodels

Install the dependencies with:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost statsmodels
```

---

## How to Run

1. Clone the repository or download the project files.
2. Prepare the datasets:
   - Download and place the `ds1.xlsx` and `ds2.csv` files in the working directory.
3. Run the script in your Python environment or upload it to Google Colab.
4. Follow the output to observe the data processing, feature engineering, model training, and evaluation steps.

---

## Outputs

- Visualizations:
  - Correlation heatmaps.
  - Feature importances.
  - EDA plots.
- Model Comparison Table:
  - Includes R², MAE, RMSE for each tested model.
- Optimized Random Forest Model:
  - Performance metrics after hyperparameter tuning.

---

## References

1. [S&P CoreLogic Case-Shiller U.S. National Home Price Index](https://fred.stlouisfed.org/series/CSUSHPISA)
2. [Redfin Market Tracker Dataset](https://redfin-public-data.s3.us-west-2.amazonaws.com/redfin_market_tracker/us_national_market_tracker.tsv000.gz)

---

## Author

This project was developed as part of a job application assignment.
