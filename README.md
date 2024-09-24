# stock_proc_pred


The goal of this project is to predict future stock prices using the Long Short-Term Memory (LSTM) neural network, a type of Recurrent Neural Network (RNN) that is particularly well-suited for time-series data. Stock market data, which consists of prices changing over time, is a prime candidate for time-series analysis, where the aim is to predict future values based on historical data.

1. Objective:
The objective of this project is to predict the closing prices of stocks based on historical data. By using LSTM, which can capture long-term dependencies in data sequences, we aim to achieve more accurate stock price predictions compared to traditional machine learning models.

2. Dataset:
The dataset used in this project includes historical stock prices such as Open, High, Low, Close, and Volume. Data is typically fetched from sources like Yahoo Finance using the yfinance library in Python. The dataset contains:

Date: The date of the stock trading day.
Open: The opening price of the stock.
High: The highest price of the stock during the day.
Low: The lowest price of the stock during the day.
Close: The closing price of the stock (usually used for prediction).
Volume: The number of shares traded during the day.
3. Steps Involved:
Data Collection:

API Integration: Using the yfinance library, historical stock data is fetched for a particular stock (e.g., Apple, Google).
Data Preprocessing: Handle missing values and irrelevant data columns like Date and Volume depending on the requirement.
Data Preprocessing:

Feature Scaling: Stock prices have different scales, so it’s essential to normalize the data to bring all values into a similar range. This is done using Min-Max Scaling, transforming data into the range [0, 1].
Creating Sequences: LSTM requires input data in the form of sequences. To create sequences, a sliding window is used to create samples where previous n days of stock prices predict the next day’s price.
LSTM Model Design:

Input Layer: The input to the LSTM model consists of time-series data over a period of days. Each input represents the stock price data for n previous days.
LSTM Layers: LSTM layers are used to capture the temporal dependencies in stock prices. LSTMs remember information over long periods, which helps in predicting the next price based on previous prices.
Dense Layer: After the LSTM layers, dense layers are added for output. The final layer has a single unit, as we're predicting one value (the stock price for the next day).
Activation Function: The model uses linear activation for the output layer since it’s a regression problem.
Training the Model:

Loss Function: The mean squared error (MSE) is used as the loss function, as this is a regression problem, and minimizing the error between predicted and actual prices is key.
Optimizer: Adam optimizer is often used to train the model due to its adaptive learning rate and efficiency with large datasets.
Model Evaluation:

Test Set Predictions: After training the model on historical data, it is evaluated using a test set (unseen data) to measure its accuracy in predicting stock prices.
Evaluation Metrics: Metrics such as Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) are used to measure the model's performance.
Visualization:

The actual vs. predicted stock prices are visualized using graphs (e.g., Matplotlib), which help in understanding how closely the model's predictions match the actual data.
Trend Analysis: By analyzing the visual plots, one can see how well the LSTM model captures the trends in stock prices.
