# Stock Price Prediction using Time Series Analysis

**Author:** Prasad Rao  
**Date:** July 31, 2025  
**Course:** Machine Learning and AI Capstone Project

## Project Overview

This project aims to develop a robust stock price forecasting model. Stock price prediction is one of the most complex to forecast, as there are many factors affecting the price. 

Following are some of the quantitative factors:
- the financial performance of the stock for the past quarter, as reported on the quarterly report
- the current price relative the financial performance. Sometimes, it is overpriced and sometimes it is under
- general trend of the larger market. For example, most of the SP500 stocks move together, at different rates, but in the same direction of the SPX index
- general trend of the sector. For example, all stocks in a sector trend to move together. If energy is up, most energy stocks join the trend

Following are some of the qualitative factors:
- the general sentiment about the company - its products, future potential, technology impacts, disruptive forces
- the analyst opinion or lack thereof. Sometimes the analysts are hyperfocused on other companies and it could be an opportunity
- the institutional interest in a company largely determines if the price will move. it is hard to predict the institution interest on a stock

 A robust price prediction must take many of the factors to predict the price.  And at the end of the day, it is merely a prediction, and the value of such a prediction is only probabilistic in nature. Only with a significant volume of trades and investments, is such a prediction useful.  
 
## Methodology
 
The projects attempts to approach this problem methodically

1. **Data Collection & Preprocessing:**

Technical Ticker data for stocks from a variety of sectors. For the project, I have collected a list of 64 tickers that are in the news and trending currently:

| Data Set | Source | Comments |
|----------|--------|----------|
| Large-Cap Tech Stocks | Financial APIs (Yahoo Finance) | Core holdings: AAPL, GOOGL, MSFT, NVDA, META, AMZN - Market leaders with 25+ year history |
| Traditional Financial Sector | Financial APIs (Yahoo Finance)  | Banks & Insurance: C, JPM, BK, BRK-B - Established financial institutions for stability analysis |
| Energy & Commodities | Financial APIs (Yahoo Finance)  | Oil & Uranium: XOM, CCJ - Traditional and clean energy exposure |
| Growth Technology Stocks | Financial APIs (Yahoo Finance)  | High-growth potential: PLTR, NET, SNOW, CRWD, ANET - Modern tech disruptors |
| Fintech & Digital Finance | Financial APIs (Yahoo Finance)  | Digital banking/trading: COIN, SOFI, HOOD, DAVE, AFRM - Next-gen financial services |
| Semiconductor Industry | Financial APIs (Yahoo Finance)  | Chip manufacturers: TSM, KLAC, NVDA, ACMR - Critical tech infrastructure |
| Cloud & SaaS Platforms | Financial APIs (Yahoo Finance)  | Enterprise software: VEEV, ZS, DOCS, SHOP - Subscription-based business models |
| Emerging Sectors | Financial APIs (Yahoo Finance)  | Space/Defense/Clean Energy: RKLB, IREN, ATAT - Frontier investment opportunities |
| Consumer & Retail | Financial APIs (Yahoo Finance)  | Traditional retail: WMT, URBN plus food delivery: DASH, TOST |
| Speculative Growth | Financial APIs (Yahoo Finance)  | Small-cap momentum: DAVE, OUST, RYTM, MIRM - Higher risk/reward positions |

Fundamental data for the same tickers:
Based on the quarterly reports that are released, we want to be able to accurately calculate the current price to book ratio (represents value at a quick glance), price to earnings ratio (represents income potential), return on invested capital (represents investor value), revenue and income trend over the past few quarters.

This is available via yahoo finance as well.

2. **Feature Development:** 

Fair price determination:

From the data research for the Capstone project, I learnt that the stock price takes 60-90 days to settle on the right price for the stock, after the quarterly report. ie., when the quarterly reports come out, the volatility is the highest for the stock, and the price varies significantly until the buyers and sellers settle down on a price and volatility and volume settles down. A predictor should quickly be able to identify the right price target, and whatever model gets this right, wins. Even if it is able to predict the direction expected would be a great start.

Price Action:

By combining STL (Seasonal and Trend decomposition) with ARIMA modeling, the project aims to predict stock prices while providing interpretable insights into market patterns and trends. 


3. **Model Selection:**



5. **Forecasting:**



6. **Validation:** 


## Technologies Used

- **Python Libraries:** pandas, numpy, matplotlib, plotly
- **Time Series Analysis:** statsmodels (STL, ARIMA, forecasting)
- **Data Source:** yfinance for stock market data
- **Visualization:** plotly for interactive charts, matplotlib for static plots

## Expected Results

The initial approach at the beginning of the project was to decompose stock price movements using the STL ARIMA process. But quickly realized that the approach was overly simplistic and the predictions were not accurate. I had to pivot to a more robust approach to include the fundamentals of the company as reported on the quarterly financial reports.  Using book value,earnings, return on invested capital, etc, I switched to prediction over the 60-90 day period. The law of averages kicks in over a longer period, and that I believe became the basis of my Capstone approach. 

Ultimately, the prediction is to be used carefully, and only over many investments. There is no guarantee that the prediction will materialize. Companies are living entities with things happening by them and to them, new product releases, a conference, a lawsuit, an investigation, expansion to new markets, new technologies. No prediction based on numbers can accurately predict any stock price accurately.


## Repository Structure

```
/
├── README.md                         # This file
├── Python Notebooks                  # Jupyter notebooks
├── data/                             # Data files (if any local data)
├── results/                          # Output charts and model results
└── requirements.txt                  # Python dependencies
```

## Getting Started

1. Clone this repository
2. Install required dependencies: `pip install -r requirements.txt`
3. Open python notebooks in Jupyter Notebook
4. Run cells sequentially to reproduce the analysis
