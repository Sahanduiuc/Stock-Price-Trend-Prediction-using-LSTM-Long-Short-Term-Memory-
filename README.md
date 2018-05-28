# Stock-Price-Trend-Prediction-using-LSTM-Long-Short-Term-Memory
# Stock-Price-Trend-Prediction-using-LSTM-Long-Short-Term-Memory





Stock Price Trend Prediction Using LSTM.




































Abstract

Predicting stock prices is always being research topic in the market and there are not even more than 100 research paper on stock predictions. As we all know Stock prices of a company depends on various features. If we are able get some features and develop a algorithm or model to predict stock prices, it won’t be accurate as the real stock prices. Therefore with some limited feature we can predict the stock price trend (is it an upwards trend or an downwards trend). As we know stocks price are time series data and there are very few algorithms or model that handle the time series data well, therefore I selected a state of the art model that is an LSTM(Long Short Term Memory) which is an Recurrent Neural Network and it performs well on time series data. Presently with all the computation power and data we can build an powerful LSTM model to predict the stock price trend.
	
Index Terms— LSTM(Long Short-Term Memory), Recurrent Neural Network, Stock Price.




































Stock Price Trend Prediction Using LSTM.



Stocks of a company are fuel that runs the whole organization. As we know that stocks are highly volatile in nature and first rule of finance is based on the Brownian motion which states that stock prices have random behavior  and are continuously changing over the time and are driven by Brownian motion process. There are many factors affecting the stock of a particular company, like Company A’s stock price depend on their rival Company B. If Company B launches a Product in market and it has a huge success so, it will affect the stock prices of  their rival Company A and visa versa. In this scenario it’s  just one company but in reality a company’s stock may be affected by it’s own decision and products as well as the products and decision of their subsidiary, dependent companies and rivals. Therefore it makes prediction of future stock prices more difficult.
As most of the research work in stock price prediction is done using financial concepts like Monte Carlo technique and by using technical indicators like Rate of change, momentum, relative index strength, average direction index etc. But in this project I am using LSTM model which is a recurrent neural network to predict the future stock prices

























Research:



Data analysis is a key step in problem solving and deep learning. First I have performed Exploratory dataset analysis to find patterns ,correlations, calculating Moving averages, Daily Returns in data [1]. Next step is problem solving here the problem is to predict the future stock prices trend.

As discussed earlier there are various ways to find future stock prices by using financial concepts like Monte Carlo technique and by using technical indicators like Rate of change, momentum, relative index strength, average direction index etc. But in this project I will be using the power of Deep learning to find the future stock prices. 

As the stock data is random and volatile, it will be difficult to predict the “Exact stock Price ” but by using LSTM and feeding it previous 60 time steps, the predicted value obtained  can much closer to the real stock price and can capture the maximum trend[3].

























Data Set Overview:

For this project I am using dataset of  Stock Prices of Apple, Google, Microsoft, Amazon.



Model Input:

[0.08545249 0.09660926 0.09393314 ... 0.07812537 0.07999865 0.08461274]  -> 0.08591389
		X_train					          y_train
 
































Prediction Approaches:

There are various way to predict Stock Prices
The most common ways using Machine learning and Deep learning  are: 
1)	Financial Concepts such as Technical Indicators and using it as feature for the machine learning model.
2)	Deep Learning with Time Series Data(Stock’s).


In the first method we calculate the following technical indicators:
1)Trend indicators
a) Moving Averages levels.
b) Parabolic Stop and Reverse (Parabolic SAR
c) Moving Average Convergence Divergence (MACD)

2) Momentum indicators
a) Stochastic Oscillator:  price range.
b)Commodity Channel Index (CCI):
c)Relative Strength Index (RSI)	

3) Volatility Indicators
a) Bollinger bands
b) Average True Range
c) Standard Deviation

4) Volume Indicators
a) Chaikin Oscillator
b) On-Balance Volume (OBV)
c) Volume Rate of Change: 

After calculating these Indicators, these indicators are used as features and feed into a Machine Learning Classification or Regression Model to Predict the Stock trend or Stock Price Respectively.[2]

This Approach gives a accuracy between 50% to 65%.









Second Approach is by using the power of Deep Learning.

Recurrent Neural Network Handle the time series Data very well. We can use RNN (Recurrent Neural Network) and predict the next day stock price as well as the stock trend(Upwards or Downwards)But for these problem RNN can handle the data as explained earlier ‘to predict the next day stock price I will feed the stock prices of last 60 days(that is 3 financial months)’.Recurrent Neural Networks face a major problem while Back-Propagation through time, this problem is know as Vanishing Gradient.This problem was solved by Sepp Hochreiter and Jugen  Schmidhuber in 1997, they came up with a solution known as LSTM (Long Short Term Memory) [6].
Long Short Term Memory:
LSTM(Long Short Term Memory) Cell.
LSTM  is a version of Recurrent Neural Network which doesn’t face Vanishing Gradient Problem and can handle the long time series data very well as compared to Traditional RNN. LSTM also can learn patterns in stock prices  which will be help for Stock Trend Prediction [2].Therefore this will be a perfect model for the our Time Series Data(Stock Prices).


Long Short Term Memory Architecture:


LSTM used in this project has the follo

Training the Long Short Term Memory Model:




Optimizer used for these model was Adam which is Adaptive Moment Estimation and combines the power of AdaGrad and RMSProp.

Loss Function or Error Function used for these model was :Mean Squared Error.

This model was  trained of 100 epochs and with batch size of 32.




We can see that First epoch had a loss of 0.475 and gradually it started to decrease and the final epoch that is 100’th epoch had a loss of 0.0014 which shows that the model had trained very well on the data.

Training Time : 3402 Seconds (56.6 Minutes.)

Training Data : Google Stock’s Open price from 2012 to 2017 (5 Years of data) 






Results:

After Training it on 5 Years of Stock price it could learn the Pattern very well .

Testing Data : 1 Jan to 31 Jan 2018.





Comparing the Predicted and Actual Prices(Google Stock’s Open Price).


We can see that the model could predict the trend (Upwards or Downwards Trend ) very well. 

The Difference in the prices are because as explained earlier the Stock Prices are very Volatile and follows the Brownian Motion Principle and there many factor affecting the stock prices. And it doesn’t only depend on previous Stock Prices.
Classification Accuracy:


Using the Actual Prices we can find the Actual Trend: 

Algorithm used for calculating the trend:

if (Next Day Open Price > Previous Day open Price): 
		Trend =  +1
else:
		Trend  = -1


+1 Denotes Upwards Trend
-1 Denotes Downwards Trend



Calculating the Accuracy Score between Actual Trend and Predicted Trend:

Accuracy Score :  0.7368421
Conclusion:


By using the power of LSTM network, we can handle the time series data very well and can capture the maximum trend. With the help of visualizations technique we can verify the real stock data and predict stock data trend. 

And the accuracy of 73.68421% (0.7368421) is also high and therefore we can conclude that the model could predict the Trend with Probability of 73.68% in the given Month of January 2018.
