# Stock Price Prediction using Time Series Analysis

**Author:** Prasad Rao  
**Date:** July 19, 2025  
**Course:** Machine Learning and AI Capstone Project

## Project Overview

This project develops a robust stock price forecasting model using advanced time series analysis techniques. By combining STL (Seasonal and Trend decomposition using Loess) with ARIMA modeling, the project aims to predict stock prices while providing interpretable insights into market patterns and trends.

## Key Features

- **Time Series Decomposition:** Separates stock price data into trend, seasonal, and residual components
- **Feature Engineering:** Creates technical indicators and lagged variables to enhance prediction accuracy
- **Model Optimization:** Systematic parameter tuning and validation for optimal performance
- **Robust Evaluation:** Uses MAE and RMSE metrics with proper train/test splits
- **Trading Expertise Integration:** Leverages practical market experience for model enhancement

## Data Sources

- **Primary Data:** Historical stock prices via Yahoo Finance API (yfinance)
- **Time Period:** 2010-2024 (Training: 2010-2018, Testing: 2019-2024)
- **Target Stocks:** Major market stocks including Citigroup (C), Tesla (TSLA), and others
- **Frequency:** Monthly data to capture meaningful trends while reducing noise

## Methodology

1. **Data Collection & Preprocessing:** Clean and prepare historical stock price data
2. **Feature Development:** Create moving averages, technical indicators, and volatility measures
3. **STL Decomposition:** Extract trend, seasonal, and residual components
4. **Model Selection:** Optimize ARIMA parameters using statistical criteria
5. **Forecasting:** Generate predictions using STL+ARIMA hybrid approach
6. **Validation:** Evaluate model performance against actual market data

## Technologies Used

- **Python Libraries:** pandas, numpy, matplotlib, plotly
- **Time Series Analysis:** statsmodels (STL, ARIMA, forecasting)
- **Data Source:** yfinance for stock market data
- **Visualization:** plotly for interactive charts, matplotlib for static plots

## Expected Results

- Accurate stock price predictions with quantified error margins
- Insights into seasonal patterns and long-term market trends
- Understanding of how different components contribute to price movements
- A reusable forecasting framework applicable to various stocks

## Stretch Goal

If time permits, the project may be extended to include sentiment analysis of financial news and social media to capture market psychology factors that complement the technical analysis.

## Repository Structure

```
/
├── README.md                          # This file
├── stock_price_prediction.ipynb       # Main Jupyter notebook
├── data/                             # Data files (if any local data)
├── results/                          # Output charts and model results
└── requirements.txt                  # Python dependencies
```

## Getting Started

1. Clone this repository
2. Install required dependencies: `pip install -r requirements.txt`
3. Open `stock_price_prediction.ipynb` in Jupyter Notebook
4. Run cells sequentially to reproduce the analysis

## Business Value

This project addresses the critical need for reliable stock price forecasting in financial markets. By combining rigorous statistical methods with practical trading insights, the model provides actionable predictions that can inform investment decisions while maintaining transparency through interpretable decomposition analysis.

---

**Note:** This project is for educational purposes as part of a Machine Learning capstone course. Past performance does not guarantee future results in financial markets.