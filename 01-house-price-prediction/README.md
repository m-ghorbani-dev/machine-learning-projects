# House Price Prediction — Divar.ir

## Overview

This project explores house-price prediction using housing data from Tehran associated with Divar.ir. The notebook covers exploratory data analysis, data cleaning, feature preparation, regression-model training, hyperparameter search, and comparison of model performance.

## Dataset

The notebook loads a CSV file named `housePrice.csv`.

The columns used in the analysis include:

- `Area`
- `Room`
- `Parking`
- `Warehouse`
- `Elevator`
- `Address`
- `Price`

The notebook also removes the `Price(USD)` column before model training. The dataset is not included in this project directory by default; place `housePrice.csv` next to the notebook before running it.

## Workflow

1. Load the dataset with pandas.
2. Explore the data using summary statistics, data types, missing-value counts, and visualizations.
3. Clean the `Area` column by removing comma separators and converting it to numeric values.
4. Remove rows containing missing values.
5. Examine feature distributions, relationships, and potential outliers.
6. Convert the boolean-style `Parking`, `Warehouse`, and `Elevator` features to integer values.
7. One-hot encode the `Address` feature.
8. Split the data into training and test sets.
9. Train and tune several regression models with `GridSearchCV`.
10. Compare models using training/test R² scores and RMSE.

## Models

The notebook compares the following models:

- Linear Regression
- Ridge Regression
- Lasso Regression
- ElasticNet
- Decision Tree Regressor
- Random Forest Regressor
- K-Neighbors Regressor
- XGBoost Regressor

## Evaluation

The notebook evaluates models using:

- **R² score** on the training and test sets
- **Root Mean Squared Error (RMSE)** on the test set

In the saved notebook outputs, the Random Forest Regressor has a test R² score of approximately **0.7768** and an RMSE of approximately **4.40 billion** in the dataset's price units. These figures reflect the run recorded in the notebook and may vary with changes to the dataset, dependencies, or execution environment.

## Technologies

- Python
- Jupyter Notebook
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- XGBoost
- joblib

## How to Run

1. Make sure Python and Jupyter Notebook or JupyterLab are installed.
2. Install the required libraries:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn xgboost joblib
   ```

3. Place `housePrice.csv` in the same directory as the notebook.
4. Open `tehran-divar-ir-house-price-prediction.ipynb` in Jupyter.
5. Run the notebook cells from top to bottom.

## Project Files

```text
01-house-price-prediction/
├── README.md
├── tehran-divar-ir-house-price-prediction.ipynb
└── housePrice.csv  # Required input data; not included by default
```

## Notes

- The notebook uses a relative path (`housePrice.csv`) to load the dataset.
- The saved notebook outputs document one execution; they are not a guarantee of future model performance.
- The model-saving and model-loading examples at the end of the notebook are currently commented out.
