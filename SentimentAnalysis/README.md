Sentimental Analysis (sentiment analysis.ipynb)
====================
Sentimental Analysis retrieve stock commentary from the market feeds and process whether it's a good or bad news and its relevant impact.

This test program is to get alphaone_free commentary feed and only process high liquidity stock in the portfolio.

1) If the security is not in the long or short list, close this position in the portfolio (sell all quantity of this security)

2) If impact == 100 & sentiment > 0.75, 

rebalance the porfolio by long 0.5 / number of long security in portfolio

order target percent according to security weight

3) If impact == 100 & sentiment < 0.75,

rebalance the portfolio by short -0.5 / number of short security in portfolio

order target percent according to security weight