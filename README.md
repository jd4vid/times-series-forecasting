# Time Series Forecasting: Temperature in Tétouan, Morocco

This project applies **time series analysis and predictive modeling** to temperature data from the city of Tétouan (Morocco).  
The dataset comes from [Kaggle: Electric Power Consumption](https://www.kaggle.com/datasets/fedesoriano/electric-power-consumption) and contains temperature readings at 10-minute intervals.  
For this analysis, the data was aggregated hourly, focusing on the first 10 days of January 2017.

## Project Objectives
- Explore the temperature time series and its components (trend, seasonality, residuals).
- Compare forecasting approaches:
  - Exponential smoothing models (Simple, Double, Holt-Winters Additive & Multiplicative).
  - ARIMA / SARIMA models (manual parameter selection).
  - AUTOARIMA for automated hyperparameter selection.
- Evaluate models with error metrics (MSE, RMSE, MAE).
- Visualize predictions with confidence intervals.

## Methodology
1. **Data Preparation**
   - Loaded temperature data.
   - Aggregated readings into hourly averages.
   - Split into training and test sets (last 24 hours reserved for validation).

2. **Exploratory Analysis**
   - Time series decomposition into trend, seasonality, and residuals.
   - Identification of hottest and coldest hours of the day.

3. **Modeling**
   - Exponential smoothing (SES, Holt, Holt-Winters).
   - ARIMA/SARIMA with parameters selected using ACF/PACF analysis.
   - AUTOARIMA for automated model discovery.

4. **Evaluation**
   - Compared models using **MSE**, **RMSE**, and **MAE**.
   - AUTOARIMA achieved the best predictive performance.

## Results
- **Best Model:** AUTOARIMA (ARIMA(2,0,2)(2,0,0)[24])
- **Performance (Test Set, 24h ahead):**
  - ARIMA Manual: RMSE = 1.75
  - AUTOARIMA: RMSE = 1.34 ✅
  - Holt-Winters Additive: RMSE = 2.22
- Visual analysis confirmed AUTOARIMA captured seasonality and trend better.

## Visualizations
The notebook includes:
- Time series plots with trend and seasonality.
- Forecast plots from all models.
- Confidence intervals for AUTOARIMA predictions.

## Tech Stack
- **Python**: pandas, numpy, matplotlib, seaborn
- **Statsmodels**: Exponential Smoothing, ARIMA, SARIMAX
- **pmdarima**: AUTOARIMA
- **Scikit-learn**: Error metrics (MSE, RMSE, MAE)

## How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/jd4vid/times-series-forecasting.git
