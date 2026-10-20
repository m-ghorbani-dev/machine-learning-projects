# Customer Churn Prediction — Telecom

## Overview

This project explores customer churn prediction in the telecommunications industry. The goal is to train a classification model that identifies customers who may leave a service and to examine how class imbalance affects model performance.

The notebook focuses on exploratory data analysis, data preprocessing, Logistic Regression, and methods for handling an imbalanced target variable.

## Dataset

The notebook loads a CSV file named `IT_customer_churn.csv`.

Place this file in the same directory as the notebook before running it. The dataset is not included in this project description, and you should check its license and redistribution terms before publishing it publicly.

The target column is `Churn`. The notebook also processes `TotalCharges` and other categorical and numerical customer features.

## Workflow

1. Import the required Python libraries.
2. Load the dataset into a pandas DataFrame.
3. Inspect column names, data types, churn distribution, and missing values.
4. Convert `TotalCharges` to a numeric type and remove rows where the value is blank.
5. Explore the data with visualizations.
6. Preprocess categorical features, including converting Yes/No values and applying one-hot encoding.
7. Scale features using `MinMaxScaler`.
8. Split the data into training and test sets.
9. Train and evaluate a Logistic Regression classifier.
10. Compare approaches for handling class imbalance:
    - Class weighting
    - Undersampling
    - Oversampling
    - SMOTE

## Model

The notebook uses **Logistic Regression** as its classification model.

## Evaluation

The notebook uses `classification_report`, which reports precision, recall, F1-score, and support for each class. It also prints the model's accuracy.

The notebook's written notes report the following observations:

- Without class weights, the minority class (churn) has precision of about `0.66` and recall of about `0.54`.
- With class weights, minority-class precision is about `0.50` and recall is about `0.79`.
- The notebook reports a minority-class F1-score of about `0.75` after undersampling.
- The notebook reports a minority-class F1-score of about `0.76` after oversampling.

These values are transcribed from notes in the notebook and should be treated as results from that recorded workflow, not as guaranteed results for every run. The notebook also includes an SMOTE workflow.

## Technologies

- Python
- Jupyter Notebook
- NumPy
- pandas
- Matplotlib
- Plotly
- scikit-learn
- imbalanced-learn

## How to Run

1. Install Python and Jupyter Notebook or JupyterLab.
2. Create and activate your preferred Python environment.
3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Place `IT_customer_churn.csv` in the same directory as the notebook.
5. Open the notebook and run the cells from top to bottom.

## Project Files

```text
02-customer-churn-prediction/
├── README.md
├── requirements.txt
├── Classification - Churn Modeling ( Telecom ).ipynb
└── IT_customer_churn.csv
```

The CSV file is required by the notebook. Include it in the repository only if its license and redistribution terms permit public sharing.

## Notes

- The notebook uses a relative path to load `IT_customer_churn.csv`.
- Results can vary with changes to the dataset, library versions, and execution environment.
- Handling class imbalance can improve recall for the minority class, but precision and other metrics may change as a trade-off.
