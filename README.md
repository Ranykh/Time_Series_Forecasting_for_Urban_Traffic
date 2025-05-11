
# Time Series Forecasting for Urban Traffic

 **Project by Rani Herbawi**  
 **Technion – Israel Institute of Technology**  
 ranykhirbawi@campus.technion.ac.il

---

## Overview

This project explores advanced time series analysis techniques to forecast **hourly urban traffic volume** at a key junction using real-world sensor data. The study compares traditional statistical models with modern machine learning approaches and evaluates the role of exogenous variables like temperature and change-point detection in improving forecasting accuracy.

---

##  Objectives

- Forecast short-term traffic volume using statistical and ML models.
- Compare the accuracy of SARIMA, Prophet, ETS, and LSTM.
- Evaluate the effect of temperature as an external (exogenous) variable.
- Identify structural shifts in traffic data through change-point detection.

---

##  Dataset

- **Source**: Kaggle [ML-IoT Traffic Dataset](https://www.kaggle.com/datasets/vetrirah/ml-iot/data)
- **Content**: Hourly vehicle counts from four urban junctions and temperture data.
- **Focus**: Junction 1 (highest variability and volume)

---

##  Models Used

| Model          | Type                  | Strengths                            |
|----------------|-----------------------|--------------------------------------|
| SARIMA         | Statistical            | Strong seasonal trend modeling       |
| Prophet        | Additive model (Meta)  | Intuitive, robust, minimal tuning    |
| Holt-Winters    | Exponential Smoothing | Lightweight, interpretable baseline  |
| LSTM           | Deep Learning (RNN)   | Captures long-term dependencies      |

---

## Exogenous Variable Analysis

- **Variable**: Ambient temperature (in Kelvin)
- **Correlation with traffic**: ~0.45 (moderate)
- **Findings**:
  - Improved SARIMAX RMSE from 17.31 → 15.43
  - Slight improvement in Prophet
  - Degraded performance in LSTM (due to noise and small dataset)

---

## Change-Point Detection

- Method: **Interrupted Time Series Regression (ITSR)**
- Detected a structural shift on **January 16, 2017 at 12:00**
- Result: Significant level shift (+12 vehicles/hour) and trend reversal post-change

---

## Performance Metrics

| Model         | MAE   | RMSE  | AIC       |
|---------------|-------|-------|-----------|
| Prophet       | 7.84  | 10.39 | –         |
| SARIMA        | 10.18 | 13.73 | 3333.26   |
| ETS           | 10.44 | 14.06 | 1907.94   |
| LSTM (Univariate) | –     | 8.24  | –         |
| LSTM (Multivariate) | –     | 11.93 | –         |

---

