# Stock-price-prediction


⸻

📈 Stock Price Prediction using LSTM

🧠 Overview

This project uses a Long Short-Term Memory (LSTM) neural network to predict future stock prices based on historical data. It involves comprehensive data preprocessing, feature engineering, sequence modeling, and deep learning techniques to forecast stock trends.

⸻

🔄 Workflow

1. Data Preprocessing
	•	Dataset Loading: Import the dataset and filter records for the stock symbol HDFCBANK with series EQ.
	•	Datetime Handling: Convert the TIMESTAMP column to datetime and set it as the index for time-series alignment.
	•	Cleaning: Drop irrelevant columns like SYMBOL, SERIES, and ISIN.

2. Feature Selection
	•	Correlation Heatmap: Analyze correlations between numerical features such as OPEN, CLOSE, HIGH, LOW, PRICE_CHANGE, VOLATILITY, etc.
	•	Feature Engineering: Choose the most relevant features to use as model inputs.

3. Data Scaling
	•	Normalization: Use MinMaxScaler to scale the features between 0 and 1, which is crucial for LSTM models.
	•	Train/Test Split: Divide the dataset into training and testing sets.

4. Sequence Generation
	•	Windowing: Generate sequential data samples using a sliding window of size 60 to help the model learn temporal dependencies (X_train, y_train, X_test, y_test).

5. Model Architecture
	•	LSTM Layers: Stack two LSTM layers:
	•	First with return_sequences=True to output full sequences.
	•	Second with return_sequences=False for final output.
	•	Regularization: Add a Dropout layer with a rate of 0.4 to reduce overfitting.
	•	Dense Output: A final Dense layer with one unit for predicting the stock price.
	•	Initialization: Use HeNormal() kernel initializer for better convergence.

6. Model Compilation
	•	Optimizer: Use the Adam optimizer for efficient training.
	•	Loss Function: Optimize using mean_squared_error, suitable for regression tasks.

7. Model Training
	•	Parameters: Train the model over 30 epochs with a batch size of 4.
	•	Validation: Validate the model using the test data during training to monitor performance.

8. Model Evaluation
	•	Prediction: Predict on both training and test sets.
	•	Inverse Transformation: Convert predictions back to the original price scale.
	•	Metrics: Evaluate model accuracy using:
	•	RMSE (Root Mean Squared Error)
	•	MAE (Mean Absolute Error)
	•	R² Score (Coefficient of Determination)

9. Future Price Forecasting
	•	Sliding Prediction: Use the last window_size values to iteratively predict prices for the next 30 days.
	•	Date Generation: Create future timestamps based on the last date in the dataset and align them with predictions.

10. Visualization
	•	Trend Analysis: Merge past actual prices with predicted future prices.
	•	Plotting: Visualize the complete trend to interpret model performance and future expectations.

⸻

✅ Conclusion
	•	A deep learning model using LSTM successfully forecasts future stock prices based on past trends.
	•	The model is evaluated using standard regression metrics like RMSE, MAE, and R² score.
	•	Future predictions can be extended or improved by refining hyperparameters, adding more features, or using hybrid models.

