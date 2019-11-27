Yahoo Price (Up to 27 Nov)
===========
Try to get stock price from 2 free quote price channel (Yahoo and Google). Google Finance claims to provide free no delay & real time quote for NYSE & NASDAQ.
https://pypi.org/project/googlefinance/

I followed the instructions above website and install Google Finance but unfortunately it doesnt work.

Conversely, Yahoo provide 15 minuate delay quote. It works for NYSE but not for Hong Kong Stock quote price.

This example desmonstrate how to use Pandas DataReader, MatplotLib.

Pandas has a simple "Remote Data Access" for the Yahoo Finance API data.

Prepare Data
============
Let us assume we are interested in working with the Close prices which have been already been adjusted by Google finance to account for stock splits. We want to make sure that all weekdays are included in our dataset, which is very often desirable for quantitative trading strategies.

Of course, some of the weekdays might be public holidays in which case no price will be available. For this reason, we will fill the missing prices with the latest available prices:

a) Initially, "CLOSE" contains all closing prices of Microsoft ("MSFT"). 

b) Some of weekdays weekdays might be missed from the yahoo data.

c) To fill up the missing data holes, we create a Series of all weekdays between the first and last date of data interval.
   Getting all weekdays is achieved by passing freq="B" in the pd.date_range() function.
   
d) This function will return "DateTimeIndex" series.

Check Data
==========
use close.describe() to check the data to return total counts,mean,standard deviation,minimum, 
25%,50%,75%,maximum

Plot 20 and 100 days moving average of close prices
====================================================

a) A simple moving average of time series is calculated by taking each date of last W prices.
  
b) pandas has rolling() which returns a rolling object for a user-defined window e.g. 20 days.

c) After a rolling object has been calculated, we can use sum(), std() - standard deviation or mean()

short_rolling_msft = msft.rolling(window=20).mean()

   



