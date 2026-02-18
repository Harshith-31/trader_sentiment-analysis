Trader Performance vs Market Sentiment
1. Objective
This project analyzes how Bitcoin market sentiment (Fear vs Greed) relates to trader behavior and performance on Hyperliquid.
The goal is to identify:
Whether profitability changes across sentiment regimes
How trader behavior shifts under Fear vs Greed
Segment-specific differences in performance
Practical strategy recommendations
2. Datasets
Bitcoin Market Sentiment Dataset
Fields:
timestamp
value
classification
date
Contains daily Fear/Greed classification.
Historical Trader Data (Hyperliquid)
Fields include:
Account
Size USD
Side
Closed PnL
Timestamp
date
Contains trade-level execution and PnL information.
3. Data Preparation
Steps Performed
Cleaned and standardized column names
Converted timestamps to datetime format
Aggregated trades at daily level
Merged trade data with sentiment data using date
Removed 6 unmatched rows with missing sentiment
Engineered Metrics
Daily PnL per account
Win rate (ClosedPnL > 0)
Average trade size (USD)
Trade frequency
Long/Short ratio
Sentiment grouping (Fear vs Greed)
4. Performance Analysis
4.1 Average Profitability
Fear mean PnL: 49.21
Greed mean PnL: 48.12
Average returns are nearly identical across regimes.
4.2 Win Rate
Fear: 40.79%
Greed: 41.34%
Greed shows a slightly higher success rate.
4.3 Risk (Volatility Proxy)
Fear std deviation: 990.87
Greed std deviation: 867.31
PnL dispersion is significantly higher during Fear.
Conclusion:
Sentiment does not materially change expected return, but Fear regimes increase volatility and potential drawdown risk.
5. Behavioral Analysis
5.1 Position Size
Fear: 7,182 USD average
Greed: 4,636 USD average
Traders deploy larger capital per trade during Fear.
5.2 Trade Frequency
Fear: 83,237 trades
Greed: 127,981 trades
Trading activity increases significantly during Greed.
5.3 Long/Short Bias
Directional exposure remains balanced in both regimes, with no strong shift in long/short ratio.
Conclusion:
Traders adjust execution style (position size vs frequency) rather than directional bias based on sentiment.
6. Trader Segmentation
6.1 High vs Low Trade Size
High-size traders significantly outperform low-size traders across both regimes.
Example (Average PnL):
High Size (Fear): 87.65
High Size (Greed): 96.55
Low Size (Fear): 2.97
Low Size (Greed): 5.17
6.2 Frequent vs Infrequent Traders
Infrequent traders:
Fear: 61.97
Greed: 121.55
Frequent traders:
Fear: 47.33
Greed: 39.43
Infrequent traders benefit significantly during Greed regimes, while frequent traders underperform.
7. Strategy Recommendations
Strategy 1 — Reduce Overtrading During Greed
During Greed regimes:
Limit trade frequency
Focus on high-conviction trades
Rationale: Infrequent traders outperform significantly during Greed periods.
Strategy 2 — Adjust Risk Exposure During Fear
During Fear regimes:
Reduce position size by 20–30%
Avoid full capital deployment
Rationale: Fear increases outcome volatility without increasing expected return.
8. Repository Structure
Trader-Sentiment-Analysis/
│
├── notebook.ipynb
├── README.md
├── requirements.txt
└── charts/
9. How to Run
Clone the repository
Install dependencies:
pip install -r requirements.txt
Open the notebook:
jupyter notebook
10. Limitations
Analysis conducted at daily aggregation level
Volatility used as a proxy for drawdown
No intraday sentiment dynamics considered
No transaction cost modeling included
