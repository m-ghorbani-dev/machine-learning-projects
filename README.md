# machine-learning-projects

# Machine Learning Projects

A portfolio of machine learning projects built with Python, covering data analysis, preprocessing, feature engineering, model training, evaluation, and practical applications.

**Status:** In progress — this repository will be updated as additional projects are added.

## Projects

| # | Project | Problem Type | Main Focus |
|---|---|---|---|
| 01 | House Price Prediction — Divar.ir | Regression | House price prediction |
| 02 | Customer Churn Prediction | Classification | Customer churn analysis and prediction |
| 03 | Salary Prediction — Stack Overflow | Regression | Salary prediction and model deployment |
| 04 | Ethereum Fraud Detection | To be confirmed | Fraud detection using Ethereum-related data |
| 05–10 | Coming Soon | — | Additional machine learning projects |

---

## 01. House Price Prediction — Divar.ir

A machine learning project focused on predicting house prices using data associated with Divar.ir.

**Project files**
- `house_price_prediction.ipynb`

**Problem type:** Regression

---

## 02. Customer Churn Prediction

A machine learning project that analyzes customer data to predict whether a customer may leave a service.

**Project files**
- `customer_churn_prediction.ipynb`
- `IT_customer_churn.csv`

**Problem type:** Classification

---

## 03. Salary Prediction — Stack Overflow

A machine learning project focused on salary prediction using Stack Overflow-related data.

**Project files**
- `salary_prediction.ipynb`
- `app.py`
- `xgbpipe.joblib`

**Problem type:** Regression

The saved pipeline is included for use by the application. The exact input features, dependencies, and execution instructions will be documented after reviewing the project code.

---

## 04. Ethereum Fraud Detection

A machine learning project exploring fraud detection using Ethereum-related data.

**Project files**
- `ethereum_fraud_detection.ipynb`

The problem formulation, algorithms, evaluation metrics, and results will be documented after reviewing the notebook.

---

## Repository Structure

```text
machine-learning-projects/
├── README.md
├── .gitignore
├── 01-house-price-prediction/
│   └── house_price_prediction.ipynb
├── 02-customer-churn-prediction/
│   ├── customer_churn_prediction.ipynb
│   └── IT_customer_churn.csv
├── 03-salary-prediction/
│   ├── salary_prediction.ipynb
│   ├── app.py
│   └── xgbpipe.joblib
└── 04-ethereum-fraud-detection/
    └── ethereum_fraud_detection.ipynb
```

This structure describes the planned organization of the first four projects. File and directory names may be adjusted to match the actual repository.

---

## Technologies

The technologies used in each project will be documented after reviewing its implementation.

The repository may include:

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Data visualization libraries
- XGBoost, if confirmed by the salary prediction implementation

---

## Getting Started

Clone the repository:

```bash
git clone git@github.com:m-ghorbani-dev/machine-learning-projects.git
cd machine-learning-projects
```

Open the notebook for the project you want to explore using Jupyter Notebook or JupyterLab.

Check each project's notebook and source files for its specific dependencies, dataset requirements, and execution instructions.

A shared `requirements.txt` and detailed setup instructions will be added after reviewing the dependencies of all projects.

---

## Data and Model Files

Some projects include datasets or serialized machine learning models.

- Check the source and license of each dataset before using or redistributing it.
- Do not publish private, sensitive, or unauthorized data.
- Only load serialized model files such as `.joblib` from trusted sources.
- Check file sizes before pushing datasets and model artifacts to GitHub. Git LFS may be appropriate for large files.

---

## Roadmap

- [x] Document the first four projects.
- [ ] Add the remaining six projects.
- [ ] Document the algorithms and preprocessing steps used in each project.
- [ ] Add model evaluation metrics and results.
- [ ] Verify project dependencies and execution instructions.
- [ ] Add visualizations and screenshots where useful.
- [ ] Add a shared `requirements.txt` if appropriate.

---

## About

This repository collects practical machine learning projects for learning, experimentation, and portfolio development.

Project descriptions, technologies, and results will be refined as each project is reviewed and added.
