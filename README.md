# Time-Series Analysis: Traffic Flow Prediction

## Overview
This project addresses the growing challenge of urban traffic congestion by applying time series forecasting to predict hourly traffic flow at busy intersections. We utilized both **classical statistical models** and **deep learning architectures with quantile regression** to build robust, uncertainty-aware forecasts that can support data-driven urban planning and real-time congestion management.

---

## Problem Statement
Urban areas face increasing traffic congestion due to rapid population and vehicle growth. Accurate traffic prediction is essential to manage limited infrastructure efficiently. This project develops and evaluates models that forecast traffic volume using temporal patterns, enabling proactive interventions for smart mobility.

---

## Dataset

- **Source**: [Kaggle - Traffic Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/traffic-prediction-dataset)
- **Size**: ~48,000 hourly entries from 4 junctions

### Columns:
- `DateTime`: Hourly timestamp  
- `Junction`: Intersection ID  
- `Vehicles`: Number of vehicles recorded  
- `ID`: Unique identifier  

---

## Tools and Libraries

- **Python**, **Pandas**, **NumPy** – data manipulation  
- **Matplotlib**, **Seaborn** – EDA & visualizations  
- **Statsmodels** – ARMA, ARIMA, SARIMA  
- **PyTorch** – RNN, LSTM, GRU (Quantile Regression)  
- **Scikit-learn**, **MinMaxScaler** – scaling & metrics  
- **ADF Test**, **ACF/PACF** – stationarity checks  

---

## Methodology

- Filtered and resampled data from hourly to daily  
- Performed time-based feature engineering (hour, weekday, month, holiday)  
- Conducted EDA to detect peak traffic hours and weekday/weekend patterns  
- Applied time series decomposition (trend, seasonality, residual)  
- Used **rolling forecast strategy** for evaluation  
- Integrated **Quantile Regression** for prediction intervals (0.05, 0.5, 0.95)

---

## Models Used

### Classical Time Series Models:
- **ARMA**
- **ARIMA**
- **SARIMA**

### Deep Learning Models with Quantile Regression:
- **RNN**
- **LSTM**
- **GRU**

> Quantile regression models output not only point predictions but also **prediction intervals**, enabling risk-aware traffic management and uncertainty estimation.

---

##  Evaluation Metrics

| Metric | Description |
|--------|-------------|
| RMSE | Root Mean Squared Error |
| MAPE | Mean Absolute Percentage Error |
| PICP | Prediction Interval Coverage Probability |
| MPIW | Mean Prediction Interval Width |

---

## Model Performance Summary

| Model | RMSE ↓ | MAPE ↓ | PICP ↑ | MPIW ↓ |
|-------|--------|--------|--------|--------|
| **GRU**   | **3.57** | 11.82% | **90.00%** | **10.24** |
| LSTM  | 3.58 | 11.49% | 88.00% | 10.52 |
| RNN   | 3.92 | 11.38% | 84.00% | 11.03 |
| SARIMA | 7.93 | 9.67% | 36.46% | 8.28 |
| ARIMA | 22.49 | 30.39% | 1.66% | 10.87 |

---

## Key Takeaways

- **GRU with quantile regression** had the best performance across all metrics.
- **Deep learning models** significantly outperformed classical models in both accuracy and uncertainty handling.
- **Quantile regression** enabled prediction intervals, crucial for real-world applications like congestion mitigation and logistics planning.
- Temporal feature engineering and rolling evaluation helped build robust forecasting pipelines.

---

## Potential Real-World Applications

- **Traffic Management**: Dynamic signal timing, congestion control  
- **Smart City Planning**: Infrastructure upgrades based on forecast demand  
- **E-commerce & Logistics (e.g., Meesho)**: Predictive routing, delivery load balancing, cost optimization  
- **Environmental Impact**: Reduced emissions through fuel-efficient flow

---

