# NVIDIA Stock Price and Tweet Sentiment Analysis

This project explores the relationship between sentiment expressed in NVIDIA-related tweets and NVIDIA (NVDA) stock prices. It uses a Hugging Face sentiment-analysis pipeline to classify tweet text as positive, neutral, or negative, then compares daily sentiment scores with historical stock closing prices.

> **Project scope:** The current notebook performs sentiment analysis and visual comparison. It does not yet train or evaluate a machine-learning model that predicts future stock prices. Correlation or visual similarity should not be interpreted as evidence that sentiment causes price movements.

## Project contents

- `stock_prediction_with_sentiment_analysis.ipynb` — notebook containing the analysis workflow.
- `Nvidia-Tweets.csv.zip` — compressed archive of the tweet dataset.
- `README.md` — project overview and instructions.
- `requirements.txt` — Python package dependencies.

## Dataset setup

The tweet dataset is stored as a ZIP archive to reduce its size in the repository.

1. Download `Nvidia-Tweets.csv.zip` from this project folder.
2. Extract the archive in the same directory as the notebook.
3. Confirm that the extracted file is named `Nvidia-Tweets.csv`.

The notebook expects the uncompressed file at `Nvidia-Tweets.csv`. If you extract it to another directory or change its filename, update the path in the notebook accordingly.

To extract the archive on Ubuntu/Linux, run this command from the project directory:

```bash
unzip Nvidia-Tweets.csv.zip
```

If `unzip` is not installed, install it with:

```bash
sudo apt install unzip
```

## Workflow

1. Load and inspect the NVIDIA tweet dataset.
2. Use the `cardiffnlp/twitter-roberta-base-sentiment-latest` model through Hugging Face Transformers to classify tweet sentiment.
3. Convert sentiment labels into signed scores: negative for negative sentiment, zero for neutral sentiment, and positive for positive sentiment.
4. Aggregate tweet sentiment by date.
5. Retrieve historical NVDA prices with `yfinance` for the relevant date range.
6. Align daily sentiment with trading dates and visualize sentiment alongside closing prices.

## Requirements

- Python 3.10 or 3.11 is recommended for compatibility with the listed libraries.
- Internet access is required to download the pretrained model on first use and retrieve historical prices from Yahoo Finance.
- Sufficient RAM and, optionally, a supported GPU can help with sentiment inference. CPU execution is also possible but may be slower.

Install the dependencies:

```bash
python -m pip install -r requirements.txt
```

Launch Jupyter Lab:

```bash
jupyter lab
```

Open `stock_prediction_with_sentiment_analysis.ipynb` and run the cells in order.

## Dataset and model notes

- The notebook reads tweet data from `Nvidia-Tweets.csv`; extract `Nvidia-Tweets.csv.zip` before running it.
- The sentiment model is downloaded from Hugging Face when it is not already cached locally.
- Stock prices are retrieved online using `yfinance`; the date range must overlap the dates in the tweet dataset for the merge and plots to contain data.
- Model scores represent confidence in a sentiment class; they are not probabilities that NVIDIA's stock price will rise or fall.

## Limitations

- Tweets may be noisy, duplicated, sarcastic, or unrelated to short-term stock movements.
- Stock markets trade on business days and have holidays, so not every tweet date has a matching stock-price row.
- Results depend on the dataset, date range, model, and preprocessing choices.
- This project is for educational and analytical purposes only and is not financial advice.

## Possible next steps

- Process all tweets in batches and save intermediate sentiment results.
- Preserve tweet IDs as strings to avoid precision loss for large identifiers.
- Evaluate whether sentiment adds predictive value using a chronological train/test split, a clearly defined target, and suitable baseline models.
