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
├── README.md                            # This file
├── 1_main.ipynb                         # Main notebook that has the final takeaways
├── 2_fundamental_data.ipynb             # Fundamental analysis workbook notebook
├── 3_correlation_and_fair_price.ipynb   # Correlation and Fair Price workbook notebook
├── 4_technical_price_prediction.ipynb   # Technical price prediction notebook
├── ticker_data/                         # Data files downloaded  from Alphavantage data service for the capstone project
├── quarterly_reports/                   # Quarterly reports data files downloaded  from Alphavantage data service for the capstone project
├── fundamentals/                        # Fundamentals files downloaded  from Alphavantage data service for the capstone project
├── earnings_data/                       # Historical Earnings Data files downloaded  from Alphavantage data service for the capstone project
├── results/                             # Output charts and model results
└── requirements.txt                     # Python dependencies
```

## Getting Started

1. Clone this repository
2. Install required dependencies: `pip install -r requirements.txt`
3. Open python notebooks in Jupyter Notebook
4. Run cells sequentially to reproduce the analysis


## Summary of Findings

### Strategies for Stock Price Prediction

Selected approximately 50 US companies that are considered trending in the summer of 2025. Based on my experience with trading and investing, I am familiar that stock price prediction is impossible due to the number of factors that can influence the price. Not just the performance results of the company, it is the market sentiment, the political conditions, economic indicators, fiscal decisions by law makers and the fed reserve, government investment in infrastructure, the geopolitical conditions. Short term predictions are almost impossible to predict.

1. Innovation and Technology stocks are favorable in Bullish Market. Consumer Staples and Utilities provide safe harbor during Bearish Market

On bullish market the hypothesis is technology and innovation stands to gain. In bearish market, money is moved to more consumer staples - everyone needs to brush their teeth. For the sector analysis, we used the SPDR ETFs. XLK, XLV, XLE, XLI, XLP, XLU, XLF, XLY, XLB, XLC, XLRE. Here are the findings:
Bull Markets: XLK (Technology) dominates and XLP (Consumer Staples) lags
Bear Markets: XLP (Consumer Staples) loses least and XLK (Technology) gets crushed

Risk-On Leaders (Bull Days): XLK, XLE, XLF - cyclical, high-beta sectors
Defensive Winners (Bear Days): XLP, XLU, XLV - consumer staples, utilities, healthcare
Energy (XLE) is extremely cyclical - 2nd best bull performer and 2nd worst bear performer
Financials (XLF) follow economic cycle - strong bull performance but heavy bear losses
Consumer Staples (XLP) are true defense - worst bull performer (+1.24%) but best bear protection (-1.33%)

Investment Strategy Implications:
Momentum Strategy: Rotate into XLK, XLE, XLF during bull markets
Defensive Strategy: Rotate into XLP, XLU, XLV during bear markets
Highest Alpha Opportunity: XLK has the widest spread (5.03%) - most timing potential
Risk Management: XLU provides consistent downside protection while still participating in upside

2. Monthly Cycles

July and November are the best months for daily returns. This is interesting for Day Traders
September is drawndown month statistically

Why is the market selling in September?

“Sell in May and Go Away”: This well-known adage suggests that the period from May to October, which includes August, tends to be weaker for stock market returns. This is supported by data from the Stock Trader’s Almanac showing the S&P 500 averaging a 7.5% return from November to April, but only 1.5% from May to October.

Summer Doldrums: August falls within the “summer doldrums,” a period of lower trading activity as many investors take vacations. This reduced volume can lead to higher volatility and potentially lower overall market performance.

Historical Performance: Over the past 20 years, the S&P 500 has averaged a 0.1% loss in August. Go back 10 years, and the average gain is a meager 0.1%, making it the third-worst month historically.

Why is the market selling in September?

“Sell in May and Go Away”: This well-known adage suggests that the period from May to October, which includes August, tends to be weaker for stock market returns. This is supported by data from the Stock Trader’s Almanac showing the S&P 500 averaging a 7.5% return from November to April, but only 1.5% from May to October.

Summer Doldrums: August falls within the “summer doldrums,” a period of lower trading activity as many investors take vacations. This reduced volume can lead to higher volatility and potentially lower overall market performance.

Historical Performance: Over the past 20 years, the S&P 500 has averaged a 0.1% loss in August. Go back 10 years, and the average gain is a meager 0.1%, making it the third-worst month historically.

Why is November an Up month?

“Sell in May” Counterpoint: Savvy investors might return to the market around Halloween (end of October) to capitalize on the historically stronger November through April period.

Potential Drivers: Some theories suggest the November effect could be related to mutual fund behavior or tax-related activities, though pinpointing a definitive cause is difficult.

Strong Recent Performance: In 2024, US stock indices like the S&P 500 and Dow Jones Industrial Average experienced strong rallies in November.

3. Quarterly Cycles

- Q1 — Tech Dominance:

XLK leads with ~0.087 risk-adjusted ratio — January tech momentum effect
Post-holiday capital rotation into growth sectors
Strong risk-adjusted performance suggests consistent Q1 tech outperformance

- Q2 — Communication Services Surge:

XLC dominates with ~0.065 — likely driven by advertising/social media earnings
XLK remains strong — continued tech momentum through spring
Q2 appears optimal for growth/tech sector overweighting

- Q3 — Materials & Industrials Leadership:

XLB (Materials) leads at ~0.065 — commodity cycle effects
XLF, XLI strong — economic activity/infrastructure themes
Summer rotation from tech into cyclical value sectors

-cQ4 — Consumer Discretionary Explosion:

XLY dominates with ~0.101 (highest single-quarter performance) — Holiday/Santa Rally
Broad-based strength across most sectors
Classic year-end risk-on environment

4. Predicting Stock Prices based on Quarterly Results

When quarterly reports are released, the stock price begins a journey of correction either to the upside or downside that usually lasts 60-90 days. Being able to correctly identify the direction in which the correction could happen, was the focus. For this I downloaded quarterly and earnings data for the stocks that were selected. 

5. Using STL, ARIMA and Quadratic Regression techniques to predict

With STL using Loess, I was able to decompose the stock price time series into three main components:

Trend - The long-term directional movement of the stock price, showing whether it's generally increasing, decreasing, or remaining stable over time

Seasonal - Recurring patterns that occur at regular intervals, such as:
- Intraday patterns (opening/closing effects)
- Day-of-week effects (Monday effect, Friday effect)
- Monthly or quarterly patterns
- Holiday or earnings season effects


Residual - The irregular, random fluctuations that remain after removing the trend and seasonal components. This represents the "noise" or unpredictable movements in the stock price

The decomposition follows the equation:
Observed = Trend + Seasonal + Remainder

I was looking for ways to predict the seasonal component. For example Amazon will be high volume around end of year shopping season and may be around the once or twice a year events like black friday sales events. This is highly subjective for each company.

For stock prices, this decomposition can be particularly useful for:

Identifying the underlying long-term direction separate from short-term volatility
Detecting recurring patterns that might inform trading strategies
Isolating the random component to better understand the stock's volatility characteristics
Forecasting by modeling each component separately

There wasnt anything conclusive about the research from this part of the exercise. 

