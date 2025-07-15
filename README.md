# Time-Series-analysis : Traffic flow prediction
Traffic Flow Prediction Using Time Series Analysis
## Overview
This project tackles the increasingly critical issue of urban traffic congestion by leveraging time series forecasting techniques to predict traffic flow at a granular level. Using both classical statistical models and modern deep learning architectures, we forecast hourly vehicle counts at city junctions based on historical data. The predictive insights generated here can aid in smarter transportation planning, optimized traffic signal control, and reduced congestion.

## Problem Statement
Urban centers face growing pressure from rising vehicle volumes and limited infrastructure. To mitigate these challenges, accurate traffic prediction is essential. This project aims to develop robust models capable of forecasting traffic volumes using past trends and temporal features, supporting data-driven urban mobility solutions.

## Dataset
Source: Kaggle - Traffic Prediction Dataset

Size: ~48,000 hourly entries across 4 junctions

## Columns:
DateTime: Hourly timestamps
Junction: Intersection ID
Vehicles: Number of vehicles
ID: Unique identifier

## Tools and Libraries
Python, Pandas, NumPy
Matplotlib, Seaborn – for EDA and visualizations
Statsmodels – ARMA, ARIMA, SARIMA
PyTorch – RNN, LSTM, GRU (Quantile Regression)
Scikit-learn, MinMaxScaler – for scaling and metrics
ADF Test, ACF/PACF – to check stationarity

## Models Used
Classical Models:
ARMA, ARIMA, SARIMA – used rolling forecasts with AIC-based tuning

## Deep Learning Models (Quantile Regression):
RNN
LSTM
GRU
All deep models were trained to predict multiple quantiles (0.05, 0.50, 0.95), enabling uncertainty-aware forecasting.

## Evaluation Metrics
Metric	Description
RMSE	Root Mean Squared Error
MAPE	Mean Absolute Percentage Error
PICP	Prediction Interval Coverage Probability
MPIW	Mean Prediction Interval Width

## Model Performance Summary
Model	RMSE ↓	MAPE ↓	PICP ↑	MPIW ↓
GRU	3.57	11.82%	90%	10.24
LSTM	3.58	11.49%	88%	10.52
RNN	3.92	11.38%	84%	11.03
SARIMA	7.93	9.67%	36.5%	8.28
ARIMA	22.49	30.39%	1.66%	10.87

## Key Takeaways
GRU performed best overall, balancing accuracy and uncertainty estimation.
Deep learning models significantly outperformed traditional ones, particularly in high-variance traffic conditions.
Feature engineering and time-based decomposition were critical in modeling temporal patterns.

## Potential Real-World Impact
Traffic management systems can use these forecasts for real-time congestion control.
Smart city planners can allocate infrastructure based on predicted demand.
Logistics and e-commerce firms (like Meesho) can integrate such models to optimize delivery routes and fleet planning.


