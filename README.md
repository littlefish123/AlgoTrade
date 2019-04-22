Python Algorithmic Trade
========================


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
   
   

Portfolio Allocation and Sharpe Ratio.ipynb
===========================================
1. How to use Quandl to get stock prices
2. Normed Returns
3. Plot Portfolio Values Graph
4. Calculate Daily Returns, Cumulative Returns, Average Daily Returns, Std Daily Returns
5. Sharpe Ratio
