# Superstore-Time-Series-Prediction

•	Total Rows: 9995
•	Total Attributes: 21

•	Column Names: Here are some important columns below:
Order Id: Represents the Id for every product 
Order Data: Represents when the product was ordered
Ship Date: Represents when the product was delivered
Sales: Represents how much sale of product was done in particular region
Quantity: Represents how many of same product were purchased.
Discount: Represents discount assigned to product
Profit: Represents profit earned from the order
Returned: Whether the product is returned or not
Our main aim is to achieve the following insights from it:
•	What is common shipping mode preferred?
•	What segmentation gives more profit to store?
•	Which state(city) specifically should store invest more?
•	Forecasting future profit estimates for different categories

## 1.	Importing Packages:
We imported necessary packages like Pandas, NumPy, Matplotlib, etc. in order to perform analysis and present visualization.

## 2.	Pre-processing Data:
The loaded data has 999 rows and 21 columns. There are no null values in the dataset. We drew descriptive statistics on the data and then prepared the data for ‘Furniture’ Sub-type forecasting.

## 3.	Building Model: 

a.	Furniture Sales Forecast: In the pre-processed data we drop all the columns except order date and sales. This was done to make the data in to a time series. Then the data was sorted by order date in an ascending order. Then the sorted time series was plotted in a line graph.
From the plotted data we can see that the highest sales were in the month of Jan 2015 and the least sales made was in February 2016. Based on the trend in the graph we can say that the approximate average sales are 250.
We then decomposed the time series in 4 components namely, Trends, Seasonality, Residuals, Observed and plotted all 4 components.
We can see an overall declining trend in the sales of the furniture as the years go by. This is a result of people renting or buying used furniture instead of buying brand new furniture. This trend is also observed because of the DIY era where a lot of people prefer making their own furniture from scratch, hence not contributing much towards the sales of new furniture. 
The seasonality shows that the furniture sales start increasing around Thanksgiving, Christmas and New Year, because people tend to redecorate houses and offices during these festive times which leads to a spike in the sales. These sales start declining soon after the first week of Jan as the busiest month kicks in, where not a lot of buying of furniture happens.
Next, we used ARIMA (1, 1, 1) x (1, 1, 0, 12) with an AIC of 263.9371084381265 as the best parameter for SARIMAX model. With this model, we generated the forecast for the future sales of furniture.
The one step-ahead forecast conditions on the training data set. Based on the forecasted sales value it can be concluded that the forecast and the observed values have quite a difference. This means that this is not the line of best fit. For the current dataset since the data is scattered widely around the regression line, we get a Mean Squared Error (MSE) of 5911.26

b.	Office Supplies Forecast: We preprocess the original Data frame to extract only the order date and sales for office supplies. We then plot the sales from Jan 2014 to Dec 2017.

From the plotted sales we can see that the highest sales were in Jan 2017 and least sales made were in Feb 2014. The overall average sales are 140. To further understand the trend in the sales of office supplies we decompose the time series.
From the decomposition we can see that there is a valley like trend in the sales of office supplies. It is higher towards the end of year 2014, falls down in the year 2015 through mid 2016 and starts increasing again from mid 2016 towards the end of 2017.
The seasonality shows that there are more sales in the months of November, December and January which starts decline from the month of February.
Next, we used ARIMA (1, 1, 1) x (1, 1, 0, 12) with an AIC of 246.479666199784 as the best parameter for SARIMAX model. With this model, we generated the forecast for the future sales of Office Supplies.

With the one step-ahead forecast we will check the performance of the model. Based on the forecasted sales value, we can conclude that the forecast and the observed values have some difference, but it is not huge. This means that this is not the line of best fit. For the current dataset since the data is scattered widely around the regression line, we get a Mean Squared Error (MSE) of 3393.63.

## 4.	Analysis:
From the two forecasts we generated we can say that both the sales show a similar seasonality of increase in sales in the months of Nov, Dec & Jan and a Steep fall in the sales in the month of Feb. Apart from this, the model is better fitted for the office supplies sales than it is for the furniture sales. 

## CONCLUSION:
From the forecasts we’ve seen for the two sales category we can say that the data is spread wide around the regression line making it difficult to predict accurate sales values. This can be improved with help of model boosting and further cleaning the data. Seasonal ARIMA forecasting uses time series data and this helps in avoiding problems that are associated with multivariate models. Seasonal ARIMA model was very useful in getting proper analysis and in getting better results. We could have improved the MSE value to a bit low by getting more data and achieved much better results.

## REFERENCES
[1] “ARIMA Model - Complete Guide to Time Series Forecasting in Python | ML+.” Machine Learning Plus, 18 Feb. 2019, https://www.machinelearningplus.com/time-series/arima-model-time-series-forecasting-python/ 
[2] Sample - Superstore Sales (Excel).Xls |Tableau Community Forums. Retrieved from:  https://community.tableau.com/docs/DOC-1236 
[3] Ritvik. Time Series Talk : ARIMA Model. Retrieved from:  https://www.youtube.com/watch?v=3UmyHed0iYE. 

