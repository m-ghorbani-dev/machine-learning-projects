# Stock Market Analysis and LSTM-Based Price Prediction

## Overview

This project explores historical market data for four technology stocks—Apple (AAPL), Alphabet (GOOG), Microsoft (MSFT), and Amazon (AMZN)—and trains an LSTM neural network to predict Apple closing prices over a held-out historical test period.

## What the notebook covers

- Downloading historical stock data with `yfinance`
- Exploring price and trading-volume history
- Calculating moving averages and daily returns
- Comparing stock returns using correlation analysis
- Visualizing a basic risk-return relationship
- Building sequences from the previous 60 trading days
- Training an LSTM model with validation-based early stopping
- Evaluating with RMSE and MAE
- Comparing LSTM predictions with a persistence baseline

## Project structure

```text
06-stock-market-analysis-lstm/
├── README.md
├── requirements.txt
└── stock-market-analysis-prediction-using-lstm.ipynb
```

## Setup

Python 3.10–3.12 is a reasonable starting point for compatibility with TensorFlow; check the TensorFlow installation guide for the version supported by your operating system and Python version.

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

On Windows, activate the environment with `.venv\Scripts\activate`.

Open the notebook with Jupyter:

```bash
jupyter notebook
```

The notebook downloads market data from Yahoo Finance, so an internet connection is required. Market data availability and the returned column structure may change over time.

## Evaluation notes

The notebook uses a chronological 95%/5% train-test split. The scaler is fitted only on the training period to avoid leaking test-period information into preprocessing. The LSTM is compared with a simple persistence baseline that predicts the next closing price using the previous close.

The test set is historical and does not represent an out-of-sample guarantee about future market prices. This project does not include transaction costs, portfolio construction, or a backtested trading strategy. It is for learning and experimentation, not financial advice.

## Data source

Historical prices are downloaded at runtime using [`yfinance`](https://ranaroussi.github.io/yfinance/). No dataset file is bundled with this project.
