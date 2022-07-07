# Statistical-Arbitrage-Research-Paper-Results
Coded the combined study of  research papers on Engle Graner Hypothesis Approach.

Engle Granger Test on Pair Trading

 Checking stationarity of data by Adfuller Test:

Adfuller Test was performed on the price to check stationary,
Result: Price of coins were non-stationary as p-value of all data was <0.05. Hence making it I(1) series. 

Adfuller Test was than performed on the consecutive difference  of prices of different coins.                                                                        Result: Consecutive difference of price of coins were stationary making us to perform our Engle Graner Approach on stationary data. Hence making it I(0) series.     

Testing for Cointegration: 
Linear Regression(Ordinary least square) was performed by selecting all pair combinations of 19 coins  in which residuals of each linear regression equation  was tested by adfuller test and all those pair coins whose residuals passed adfuller test (p_value>0.05) were stored in the dataframe pair[(i,j)] with their names representing  i and j and holding their respective value of residuals.                                                                                                

Error Correction Modelling:

ECM equation is  a*yt= b*xt  +  c*x(t-1) + d*res + e.                                                                                                             where  t → current time, x → difference in consecutive price of coin X, y → difference in consecutive price of coin Y , res → pair([x,y]), t-1 → lag of 1 unit of time, e → constant added for removing sort of overfitting.

Generally value of c is between -1 to 0 which will make coin to revert back to its mean position in short term.                                                     So value of c was stored in dataframe sel_pair1['error_coeff'] and sorted in ascending value the coin with most negative c value is our ideal pair for mean reversion trading.                                                                     
Pair Selection Done.    

Spurious Regression issue was checked from R-squared metric comparison with Durbin Watson statistic and t-statisitc.

To Do:
To apply the strategy on rolling basis to check for results on sample of weeks.

Drawback:
Hedge Ratio was calculated at once, Hedge ratio might dont get estimated significantly.
