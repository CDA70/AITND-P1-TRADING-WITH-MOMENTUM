# AITND-P1-TRADING-WITH-MOMENTUM
This is the first project in the nanodegree, artificial intelligence for trading

The aim is to implement a trading strategy and test to see if has the potential to be profitable. Supplied are a universe of stocks and time range. 

The project requires to implement some functions:

## Resample Adjusted Prices
The trading signal for this project isn't based on daily prices, and therefore a resample of the daily adjusted closing prices into monthly buckets is performed

## Compute Log Returns
Compute the log returns (Rt) from prices (Pt) for each ticker and date
 
 ` Rt = log e(Pt) - log e(Pt-1) `
 
## Shift Returns
Implement a shift_return function to shift the log returns to the previous or future returns in the time series. The parameter shift_n is 2 and returns is the following and shifts the stocks in the future, if it's a negative number, the stock are shift in the past

## Generate Trading signal
A trading signal is a sequence of trading actions, or results that can be used to take trading actions. A common form is to produce a "long" and "short" portfolio of stocks on each date (e.g. end of each month, or whatever frequency you desire to trade at). This signal can be interpreted as rebalancing your portfolio on each of those dates, entering long ("buy") and short ("sell") positions as indicated.

We tried to implement the following:

For each month-end observation period, rank the stocks by previous returns, from the highest to the lowest. Select the top performing stocks for the long portfolio, and the bottom performing stocks for the short portfolio.

Implementing the get_top_n function is to get the top performing stock for each month. 

## Projected Returns
Here we check the trading signal if it has the potential to become profitable.

Therefore we compute the net returns that this portfolio would return. For simplicity, we'll assume every stock gets an equal dollar amount of investment. This makes it easier to compute a portfolio's returns as the simple arithmetic average of the individual stock returns.

Implement the portfolio_returns function to compute the expected portfolio returns. Using df_long to indicate which stocks to long and df_short to indicate which stocks to short, calculate the returns using lookahead_returns. 

## T-TEST
The null hypothesis ( 𝐻0 ) that the actual mean can return from the signal is zero. We  performed a one-sample, one-sided t-test on the observed mean return, to see if it can reject 𝐻0.

First compute the t-statistic and then find it's corresponding p-value. The p-value will indicate the profitability of observing a t-statistic equally or more extreme than the one that is observed in the null hypothesis were true.

A small p-value means that the chance of observing the t-statistic we observed under the null hypothesis is small, and thus casts doubt on the null hypothesis. It's good practice to set a desired level of significance or alpha ( 𝛼 ) before computing the p-value, and then reject the null hypothesis if  𝑝 < 𝛼.

For this project, we'll use  𝛼=0.05 , since it's a common value to use

# RESULT
In our test the alpha was set as 0.05, the result above show a value (0.073359) > 0.05, therefore we cannot reject the null hypothesis and moreover we can conclude that the strategy doesn't contains an alpha.





