Python Algorithmic Trade
========================

Pairs Trading (pairtrading.ipynb)
=================================
Develop on top of Quantopian Platform which access the historial prices & stock fundamentals. This platform provides backtest with historial stock period.

Pairs trading is a strategy that uses two stocks that are highly correlated. It use the difference in price between the two stocks as signal if one moves out of correlation with the other. 

1. Find out correlation between 2 stock spread
2. Calculate 1 Day and 30 Day Spead Moving Average Line
3. Normalize Spread Moving Average
4. Draw Mean line, -10% / 10% percent up Mean Line 
5. Implement the trading strategy :
	Check by end of 30 minutes of close market of every trade day
	If normalize spread rate > 0.5 
		Rebalance portfolio by (1) Short AA (2) Long UAL 
	If normalize spread rate < -0.5
		Rebalance portfolio by (1) Long AA (2) Short UAL

porfolio.ipynb
==============

Python program to calculate the maximum weights of stock portfolio based on the "Modern Portfolio Theory", based on risk-averse investors can construct portfolios to optimize or maximize expected return based on a given level of market risk, emphasizing that risk is an inherent part of higher reward. It is one of the most important and influential economic theories dealing with finance and investment.

This program illustrates how to use the following methodogy :
1) Monte Carlo Simulation
    a) Arithmetric Returns
    b) Log Returns
    
2) Mathematical Optimization
Optimization works as a minimization function, since we actually want to maximize the Sharpe Ratio, we will need to turn it negative so we can minimize the negative sharpe (same as maximizing the postive sharpe)

    a) Sequential Least SQuares Programming (SLSQP) to find out the minimum point among negative sharpe ratio, ie. Optimized Portfolio
    b) Efficient Frontier to find out set of optimal portfolios 
The efficient frontier is the set of optimal portfolios that offers the highest expected return for a defined level of risk or the lowest risk for a given level of expected return. Portfolios that lie below the efficient frontier are sub-optimal, because they do not provide enough return for the level of risk. Portfolios that cluster to the right of the efficient frontier are also sub-optimal, because they have a higher level of risk for the defined rate of return.

ARIMA.ipynb
===========
ARIMA (AutoRegressive Integrated Moving Average Model) is the generalization of ARMA Model (AutoRegressive Moving Average Model) to predict the future prices.
1. Non-seasonal ARIMA
2. Seasonal ARIMA

Data show evidence of non-stationary, where an initial differencing steps (corresponding to the "Integrated" part of model) can be applied one or more times to eliminate the non-stationary.
Non-seasonal ARIMA are denoted by ARIMA(p,d,q)
AR (p) : Autoregression - A regression model utilizes depedendent relationship between a current observation and observations over a previous period
I(d) : Integrated - Differencing of observations in ordre to make the time series stationary.
MA (q) : Moving Average - A model uses dependency between an observation and a residual error from a moving average model applied to lagged observations.

1. Use "Augmented Dickey Fuller Test" to test for stationarity of data.
2. Transform to stationary in order to evaluate it (continue differencing in each step until data reach stationary)
3. Each differencing step comes of losing a row of data.
4. For seasonal data, e.g. monthly data with yearly seasonality, you could difference by a time unit of 12 instead of 1.
5. After the data come into stationary, use "AutoCorrelation Plot" (Correlogram) and "Partial AutoCorrelation Plot"
    y axis - correlation
	x axis - number of time units of lag.
   Determine whether Sharp Drop off or Gradual Decline from the plot graph.
   
6. Figure out to 1. use AutoRegression (AR) or Moving Average (MA) 2. how many lags to use by:
    a) If autocorrelation plot show negative autocorrection at first lag => use MA
	b) p: The number of lag observations 
	   q: The number of times that the raw observationst to be diferenced
	   q: size of moving average window (order of moving average)
	c) For example, a Sharp Drop in Partial Autocorrelation PLot after lag "k" suggests to use "AR-k" model. (by Partial AutoCorrelation Plot)
	   For example, a Gradual Decline suggests to use MA Model (by AutoCorrelation Plot)

7. Predict the future prices by extending the future date period.	   
   
   
Capital Assets Pricing Model CAPM.ipynb
=======================================
CAPM describe risk and separating market return versus your portfolio return.

Portfolio Return Rp(t) = Summation of Weight(i) X R(i)(t)

e.g. Entire market = S&P500
Market Cap of S&P500 = W(i) = MarketCap(i) / Summation of MarketCap(j)

CAPM Equation :
Ri(t) = Beta-i * Rm(t) + Alpha-i(t)

 Return of a Stock is equivalent to the "return of market" multiplied by "Beta factor" plus "residual Alpha".
 
 If Beta=1, stock move in line with the market
 If Beta-2, stock move up twice as market
 
 Active Investors believe we can predict Alpha (only more than 50% correct would be fine)
 
 Rp(t) = Beta-p * Rm(t) + Summation of Weight(i) * Alpha(i)(t)
 
 Alpha-i(t) = Summation of Weight(i) * Alpha(i)(t)
 



Portfolio Allocation and Sharpe Ratio.ipynb
===========================================
1. How to use Quandl to get stock prices
2. Normed Returns
3. Plot Portfolio Values Graph
4. Calculate Daily Returns, Cumulative Returns, Average Daily Returns, Std Daily Returns
5. Sharpe Ratio
