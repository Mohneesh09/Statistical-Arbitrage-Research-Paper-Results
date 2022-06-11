# Statistical-Arbitrage-Research-Paper-Results
Coded the combined study of 3 research papers on Engle Graner Hypothesis Approach.
Engle Graner Test on Pair Trading
Created by 
Last updated:  by 5 min read3 people viewed
     Checking stationarity of data by Adfuller Test:

Adfuller Test was performed on the price to check stationary,                                                               Result: Price of coins were non-stationary as p-value of all data was <0.05. Hence making it I(1) series. 

Adfuller Test was than performed on the consecutive difference  of prices of different coins.                                                                                                                                Result: Consecutive difference of price of coins were stationary making us to perform our Engle Graner Approach on stationary data. Hence making it I(0) series.                                                                                         Testing for Cointegration: 

Linear Regression(Ordinary least square) was performed by selecting all pair combinations of 19 coins  in which residuals of each linear regression equation  was tested by adfuller test and all those pair coins whose residuals passed adfuller test (p_value>0.05) were stored in the dataframe pair[(i,j)] with their names representing  i and j and holding their respective value of residuals.                                                                                                                                     Error Correction Modelling:

ECM equation is  a*yt= b*xt  +  c*x(t-1) + d*res + e.                                                                              where  t → current time, x → difference in consecutive price of coin X, y → difference in consecutive price of coin Y , res → pair([x,y]), t-1 → lag of 1 unit of time, e → constant added for removing sort of overfitting.

Generally value of c is between -1 to 0 which will make coin to revert back to its mean position in short term.                                                                                                                                                               So value of c was stored in dataframe sel_pair1['error_coeff'] and sorted in ascending value the coin with most negative c value is our ideal pair for mean reversion trading.                                                                     Pair Selection Done.                                                                              

RESULTS: 

7 days time frame(21/05/22 to 28/05/22) (1 min tick interval):

Best pair:  (BTC, ETH)


1Total Profit is 981.0400000000009
Profit

 

count

10.000000

mean

98.104000

std

449.187866

min

-639.870000

25%

-297.357500

50%

365.760000

75%

389.662500

max

421.790000  

 

2) 15 days time frame(15/05/22 to 30/05/22) (1 min tick interval):

    Best pair: (MANA, ADC)


1Total Profit is 0.20389999999999986
Profit

 

count

3.000000

mean

0.067967

std

0.003573

min

0.065200

25%

0.065950

50%

0.066700

75%

0.069350

max

0.072000

 

3) 30 days time frame(30/04/22 to 30/05/22) (1 min tick interval):

Best Pair: (SUSHI, BNB)


1Total Profit is 112.06499999999988
Profit

 

Profit

 

count

3.000000

mean

37.355000

std

0.782575

min

36.734000

25%

36.915500

50%

37.097000

75%

37.665500

max

38.234000

All the profits calculated were without considering hedge ratio but would be considered in next testing.

 

To Do:

To apply the strategy on rolling basis to check for results on sample of weeks.

To test the process on higher  Tick Interval.(preferably 5 min, 1 Day).

To consider hedge ratio in further calculation.
