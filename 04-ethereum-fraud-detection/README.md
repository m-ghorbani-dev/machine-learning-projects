# Ethereum Transaction Fraud Detection

This project explores fraudulent and legitimate Ethereum-related transactions using exploratory data analysis and machine-learning classification. The notebook compares Logistic Regression, Random Forest, and XGBoost, and uses SMOTE to address class imbalance in the training data. It also performs hyperparameter tuning for XGBoost with `GridSearchCV`.

## Project contents

- `how-to-detect-fraud-in-crypto.ipynb` — notebook containing data exploration, preprocessing, model training, evaluation, and visualizations.
- `transaction_dataset.csv` — dataset used by the notebook.
- `README.md` — project overview and instructions.
- `requirements.txt` — Python dependencies.

## Dataset

The dataset contains 9,841 rows and 51 columns in the supplied CSV file. It includes the `FLAG` target column, where the notebook treats `0` as non-fraudulent and `1` as fraudulent, account addresses, transaction activity, Ether values, and ERC-20-related features.

The notebook describes the dataset source as Kaggle:

- https://www.kaggle.com/datasets/vagifa/ethereum-frauddetection-dataset

Keep `transaction_dataset.csv` in the same directory as the notebook. The notebook loads it using:

```python
df = pd.read_csv("transaction_dataset.csv", index_col=0)
```

## Analysis workflow

1. Load the dataset and inspect its structure and target distribution.
2. Explore feature distributions and correlations.
3. Remove categorical columns and handle missing numeric values using median imputation.
4. Remove zero-variance and selected highly correlated or mostly-zero features.
5. Split the data into training and test sets.
6. Standardize the feature data and apply SMOTE to the training data.
7. Train and evaluate Logistic Regression, Random Forest, and XGBoost classifiers.
8. Tune XGBoost hyperparameters with cross-validation using recall as the scoring metric.
9. Review classification reports, confusion matrices, and an ROC curve.

## Requirements

Python 3.10 is a reasonable starting point for setting up this notebook, especially because the notebook also uses PyCaret. Package compatibility can vary by Python and library version.

Create and activate a virtual environment (optional but recommended):

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the dependencies:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter lab
```

Open `how-to-detect-fraud-in-crypto.ipynb` and run the cells in order. The notebook includes PyCaret setup and model comparison, so PyCaret must be installed for those cells. The notebook also downloads or uses the installed machine-learning libraries.

## Evaluation and interpretation

The notebook evaluates the models using classification reports, confusion matrices, recall-oriented XGBoost tuning, and an ROC curve. In fraud detection, recall for the fraud class is important because false negatives represent fraudulent cases the model fails to flag. However, recall should be considered alongside precision and false-positive rates.

SMOTE is applied to the training split rather than the test split. Treat the reported results as an educational experiment; they may change with package versions, preprocessing choices, and model parameters.

## Limitations

- The dataset is a static dataset and may not represent current Ethereum activity or future fraud patterns.
- A random train/test split may not reflect performance on future transactions.
- The notebook removes selected features based on correlation and distributions; those choices may affect results.
- The notebook's ROC plot section labels the chart as tuned XGBoost, but the code uses `xgb_c.predict_proba`, which is the untuned XGBoost model. Change it to `grid.best_estimator_.predict_proba(sc_test)` if the intention is to plot the tuned model.
- This project is for learning and experimentation, not for making real-world fraud decisions without further validation.

## Possible next steps

- Use a scikit-learn `Pipeline` to keep preprocessing and model fitting consistent.
- Compare precision, recall, F1-score, PR-AUC, and ROC-AUC on a held-out test set.
- Evaluate with stratified cross-validation and document the final selected model's metrics.
- Save the trained model and preprocessing objects for reproducible inference.
