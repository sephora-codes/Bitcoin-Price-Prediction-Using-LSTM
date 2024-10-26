# Bitcoin-Price-Prediction-Using-LSTM
Bitcoin price prediction using Long Short-Term Memory (LSTM) models is a popular application of deep learning in time series forecasting. Bitcoin’s price is highly volatile and influenced by various factors such as market demand, regulatory news, technological advancements, and investor sentiment. Here’s a description of a project on predicting Bitcoin prices using an LSTM model:

Project Overview:
The aim of this project is to predict the future price of Bitcoin by analyzing historical price data using an LSTM neural network, a type of recurrent neural network (RNN) that is particularly effective for time series data because of its ability to capture long-term dependencies.

Steps Involved:
Data Collection:

Gather historical Bitcoin price data from sources like Yahoo Finance, CoinMarketCap, or other crypto APIs. This dataset typically includes attributes such as opening price, closing price, high, low, trading volume, and date.
Choose the prediction target, e.g., closing price.
Data Preprocessing:

Normalization: Scale the data to a range between 0 and 1 (or -1 to 1) using a MinMaxScaler to improve model performance.
Feature Selection: Select relevant features that may impact Bitcoin price, such as past prices, trading volume, etc.
Train-Test Split: Split the dataset into training and testing sets. Usually, the first part is used for training, and the latter part is used for testing to simulate real-world scenarios.
Create Sequences for Time Series:

LSTMs require input data to be in a sequence format. For each data point, create sequences of a specific time window (e.g., 30 days of previous data points) that the LSTM will use to predict the next price point.
For example, if you use a 30-day window, the model will learn to predict the price on day 31 based on data from the previous 30 days.
Build the LSTM Model:

Define Model Architecture: The model typically consists of one or more LSTM layers followed by dense layers to output the prediction.
Example Architecture:
1st LSTM layer with 50-100 units and return_sequences=True (if stacking layers)
2nd LSTM layer with 50-100 units and return_sequences=False
Dense layer(s) to reduce the output to a single price prediction
Compile the Model: Use mean squared error (MSE) as the loss function and Adam optimizer, commonly used for regression problems.
Train the Model:

Train the model on the training data, specifying the number of epochs (e.g., 50-100) and batch size (e.g., 32).
During training, the LSTM will learn patterns in the data and adjust weights accordingly.
Evaluate Model Performance:

After training, evaluate the model on the test dataset using metrics like mean squared error (MSE) or mean absolute error (MAE) to assess accuracy.
Make Predictions:

Use the trained model to make predictions on the test set or future data.
Rescale the predicted values back to the original scale (if normalized) for interpretability.
Visualization:

Plot the actual vs. predicted Bitcoin prices on a graph to visualize model performance.
This helps in assessing how closely the model’s predictions align with the real Bitcoin price movements.
