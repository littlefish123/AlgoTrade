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

Portfolio Allocation and Sharpe Ratio.ipynb
===========================================
1. How to use Quandl to get stock prices
2. Normed Returns
3. Plot Portfolio Values Graph
4. Calculate Daily Returns, Cumulative Returns, Average Daily Returns, Std Daily Returns
5. Sharpe Ratio
