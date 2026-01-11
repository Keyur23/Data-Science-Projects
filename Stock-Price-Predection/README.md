# Stock Price Prediction using LSTM

## Overview

This project implements a **Long Short-Term Memory (LSTM)** neural network to predict Netflix stock prices. The model uses historical stock data to forecast future price movements, demonstrating the application of deep learning in financial time series forecasting.

## Dataset

The project uses Netflix historical stock price data (`Netflix_Dataset.csv`) with the following features:
- **Date**: Trading date
- **Open**: Opening price
- **High**: Highest price during the trading day
- **Low**: Lowest price during the trading day
- **Close**: Closing price
- **Volume**: Trading volume

The dataset spans from March 2019 to March 2022, providing comprehensive historical data for training and testing the prediction model.

## Technologies Used

- **Python 3.10**
- **TensorFlow/Keras**: Deep learning framework for building LSTM models
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Matplotlib**: Data visualization
- **Scikit-learn**: Data preprocessing and model evaluation

## Project Workflow

1. **Data Loading**: Import Netflix stock price data from CSV file
2. **Data Preprocessing**: 
   - Handle missing values
   - Normalize data using MinMaxScaler
   - Create time series sequences for LSTM input
3. **Model Architecture**:
   - LSTM layers for capturing temporal patterns
   - Dense layers for final prediction
   - Designed to learn complex patterns in stock price movements
4. **Model Training**: Train the LSTM network on historical data
5. **Prediction**: Generate stock price predictions on test data
6. **Evaluation**: Assess model performance using:
   - **RMSE (Root Mean Squared Error)**: 0.0586
   - **MAPE (Mean Absolute Percentage Error)**: 5.92%
7. **Visualization**: Compare true values vs. LSTM predictions

## Key Results

The LSTM model achieved:
- **RMSE**: 0.0586
- **MAPE**: 5.92%

These metrics indicate that the model provides reasonably accurate predictions despite the inherent complexity and volatility of stock price data. The visualization shows that the model successfully captures the overall trend of stock price movements.

## Key Findings

- LSTM networks are effective for time series prediction in financial markets
- The model achieved decent performance metrics despite data complexity
- Creating deeper networks did not significantly improve test performance, suggesting the current architecture is well-balanced
- The model captures general trends but may struggle with sudden market fluctuations

## How to Run

1. Ensure you have the required dependencies installed:
   ```bash
   pip install pandas numpy tensorflow matplotlib scikit-learn
   ```

2. Open the Jupyter notebook:
   ```bash
   jupyter notebook main.ipynb
   ```

3. Run all cells sequentially to:
   - Load and preprocess the data
   - Build and train the LSTM model
   - Generate predictions and visualizations
   - Evaluate model performance

## Future Improvements

- Incorporate additional features (technical indicators, market sentiment, etc.)
- Experiment with different LSTM architectures (bidirectional LSTM, attention mechanisms)
- Implement ensemble methods combining multiple models
- Add feature engineering for better prediction accuracy
- Extend prediction horizon for longer-term forecasts

## Use Cases

This project demonstrates practical applications in:
- **Financial Forecasting**: Predicting stock prices for investment decisions
- **Risk Management**: Understanding price volatility patterns
- **Trading Strategies**: Developing data-driven trading algorithms
- **Portfolio Management**: Supporting buy/sell decision-making

## License

This project is open-source and available for educational purposes.
