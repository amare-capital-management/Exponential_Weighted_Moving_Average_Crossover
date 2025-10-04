<img width="780" height="253" alt="ACM w color" src="https://github.com/user-attachments/assets/b068a0ab-bbe7-426d-81d8-a1c70c9c2a74" />

### The 5.Exponential_Weighted_Moving_Average_Crossover.py script implements an Exponential Weighted Moving Average Crossover (EWMAC) strategy for systematic trading. Here's a detailed breakdown of its functionality:

*1. Overview:*

The script calculates fast and slow exponentially weighted moving averages (EWMAs) for stock prices.
It generates trading signals based on the difference between the fast and slow EWMAs, adjusted for volatility.

*2. Parameters:*

Tickers: A predefined list of stock tickers to analyze.
Start and End Dates: Defines the time range for historical data.
EWMAC Parameters:
Lfast: Lookback period for the fast EWMA.
Lslow: Lookback period for the slow EWMA (4 times Lfast).
vol_lookback: Lookback period for volatility calculation.
capmin and capmax: Limits for capping the forecast signal.
Data Retrieval:
retry_download: Fetches historical OHLC (Open, High, Low, Close) data for each ticker using Yahoo Finance. Retries up to 3 times in case of failure.

*3. EWMAC Calculation:*

Fast and Slow EWMAs: The fast EWMA reacts quickly to price changes, while the slow EWMA reacts more slowly.
Raw Signal: The difference between the fast and slow EWMAs.
Volatility Adjustment: Adjusts the raw signal by dividing it by the exponentially weighted standard deviation of price returns.
Forecast Signal: Scales the volatility-adjusted signal using a scalar derived from Lfast and caps it within the range [capmin, capmax].

*4. Visualization:*

For each ticker:

Price Chart: Plots the stock price along with the fast and slow EWMAs.
Forecast Signal Chart: Plots the capped forecast signal with buy/sell thresholds.
Saves the charts in the ewmac_charts folder.

*5. Signal Generation:*

Collects the latest forecast signal for each ticker and stores it in a list.

*6. Output:*

Charts: Saves EWMAC charts for each ticker.
Summary CSV: Saves the latest forecast signals for all tickers in EWMAC_signals.csv.

*Purpose:*

This script is a quantitative trading tool designed to:

Identify potential buy/sell opportunities based on the EWMAC strategy.
Visualize the relationship between price movements and EWMAs.
Generate a summary of trading signals for further analysis.

### It is useful for traders and analysts looking to implement or backtest a systematic trading strategy based on moving average crossovers.
