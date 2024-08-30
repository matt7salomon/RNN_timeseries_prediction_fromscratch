# RNN_timeseries_prediction_fromscratch

Locational Marginal Prices Prediction
Matt Salomon

The 15-minute Locational Marginal Prices (LMP) data were downloaded from CAISO OASIS platform. The prices in this dataset reflect the current status of the market. The LMP prices were downloaded for three separate nodes. Recursive Neural Networks (RNN) and ARIMA were selected to predict the prices in the future from current values. These models perform well on time series data since they consider a window of time and roll the window over the data. 44 days of data were downloaded for each node since it was the maximum that OASIS allowed to download in one session. Arima allows for only one time series to be forecasted at a time so it doesn’t allow for additional features to be considered. To keep matters consistent and have similar comparison, the same time series were predicted using an RNN. Root mean squared error (RMSE) was considered as the performance metric since we are comparing two time series together(i.e. the original data and the predicted data).

 Arima showed the following performance on Node 0096WD_7_N002 were the blue line is the actual LMP and the red line is the prediction:

 
The test RMSE for ARIMA is as follows:

Test RMSE: 9.266

The data were split into 67% training data and 33% test for the RNN to analyze the performance of the model accurately. Model is trained on the train dataset and performance of the model is tested using the test dataset.

RNN showed following results for train and test data for Node 0096WD_7_N002:

 
Blue represents the actual data, yellow represents prediction on train data, and green represents prediction on test data.

RNN showed the following root mean squared error on train and test data:

Train Score: 9.52 RMSE
Test Score: 7.84 RMSE


From this experiment we learned that LMP has a seasonality effect in it which makes the prediction possible for the next time window based on current time window. LMP seems to be lower at night than during the day and it seems to be highest in middays. The trend, seasonality, and residue can be found in the following picture.

 
 
