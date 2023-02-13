# time_series
## Project purpose
A taxi company has collected historical data on taxi orders at airports. To attract more drivers during the peak period, we need to predict the number of taxi orders for the next hour. It is necessary to build a model for such a prediction with RMSE on the test sample is less than 48.
## Summary 
* Revealed that our time series is stationary
* Identified a trend - the total number of taxi orders is increasing.
* Found hourly seasonality: 3 peak orders fall on periods from 8 to 10, from 15 to 17, from 22 to 01 hours. At the same time, every day the absolute minimum of orders falls on the time around 6 o'clock in the morning.
* Revealed weekly seasonality: the minimum of orders falls on Tuesdays and Sundays, the maximum - on Mondays and Fridays.
* Created additional features: calendar (month, day, day of the week, hours), previous values with a lag size of 1-5 hours, moving averages with a window width of 3 hours, by day (24 hours) and for 3 days. Additionally, a column was created that contains the difference between the number of orders in the previous and previous hours.
* Trained 3 different models: linear regression, random forest and gradient boosting from the CatBoost library.
* The random forest in regression model (RMSE - 25.09) did the best on the training sample, the worst of all was the linear regression model (RMSE - 31.04).
* The best model (random forest model in regression with hyperparameter n_estimators=9) on the test set shows the RMSE metric of 46.55.
