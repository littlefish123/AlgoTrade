Pairs Trading (pairtrading.ipynb)
=================================
Develop on top of Quantopian Platform which access the historial prices & stock fundamentals. 
This platform provides backtest with historial stock period.

Pairs trading is a strategy that uses two stocks that are highly correlated. 
It use the difference in price between the two stocks as signal if one moves out of correlation with the other. 

1. Find out correlation between 2 stock spread

2. Calculate 1 Day and 30 Day Spead Moving Average Line

3. Normalize Spread Moving Average

4. Draw Mean line, -10% / 10% percent up Mean Line 

5. Implement the trading strategy :

(a) Check by end of 30 minutes of close market of every trade day

(b) If normalize spread rate > 0.5, Rebalance portfolio by (1) Short AA (2) Long UAL 

(c) If normalize spread rate < -0.5, Rebalance portfolio by (1) Long AA (2) Short UAL

