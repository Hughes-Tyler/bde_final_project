# bde_final_project

Stock Sentiment Prediction Project

This project looks at whether news sentiment can help predict short-term stock price direction. I used Tesla (TSLA) and Apple (AAPL) as examples, combining public news data with historical stock prices.

The project goes through the full data science process: collecting data, cleaning it, creating features, training models, evaluating performance, and finally making predictions on new data through an Excel input template.

## Overview

### Data Collection

News headlines were pulled from Google News RSS feeds using feedparser.

Each title was analyzed with the VADER sentiment analyzer to measure sentiment polarity.

The results were summarized daily and saved to CSV files.

Historical price data was downloaded from Yahoo Finance using yfinance.

### Feature Engineering

Technical indicators include moving averages, RSI, MACD, Bollinger bands, and volatility.

Sentiment features include average polarity, rolling sentiment, ratios, and z-scores.

These were merged into one dataset per stock.

### Modeling

Built models to predict if the stock would go up or down over the next 3 days.

Compared Logistic Regression, Random Forest, and XGBoost.

XGBoost performed best based on ROC-AUC and accuracy.

### Saving and Prediction

Models, scalers, and imputers are saved in the Models folder with joblib.

The final XGBoost pipeline is used in a prediction script that reads a one-row Excel file and prints a predicted direction and probability.

## Folder Structure

FINAL_PROJECT
│
├── Code/ (main notebook and scripts)
├── Input_Data/ (CSV files for sentiment and stock data)
├── Models/ (saved models and preprocessing files)
├── Template/ (Excel template for single predictions)
└── requirements.txt

##How to Run

Clone or download the project.

Install dependencies:
pip install -r requirements.txt

Open the notebook in the Code folder and run all cells in order. Depending on your computer type, you may need to use something like Google Colab for running the first cell.

To test a prediction, open Template/prediction_template.xlsx, fill in one row with feature values, and run the final prediction cell in the notebook.

##Results

Sentiment data improved performance slightly, especially during volatile periods.

##Notes

You can easily adapt it for other tickers by changing the stock symbol at the top of the notebook.
