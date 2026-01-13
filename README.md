# Forecasting Monthly Average Temperature in Rome

**Author:** Antonella Convertini  
**Course:** Data Science for Economics  
**Institution:** Università degli studi di Milano  

---

## 📌 Project Overview
This project implements a complete time-series forecasting analysis for monthly average temperatures in Rome (Ciampino Station). The goal is to model historical temperature dynamics and generate reliable future forecasts using **SARIMA** and **SARIMAX** models.

The analysis covers the period from **January 1951 to September 2022**, exploring the impact of seasonality, precipitation, and global climate indices like the **ENSO (El Niño-Southern Oscillation)** on local temperatures.

### Key Objectives
1.  **Exploratory Data Analysis (EDA):** Analyze trends, seasonality, and stationarity of the temperature time series.
2.  **Model Selection:** Compare varying model architectures (SARIMA vs. SARIMAX with covariates).
3.  **Forecasting:** * Evaluate performance on a hold-out test set (RMSE, MAE, MAPE).
    * Generate a **10-year future forecast** scenario.

---

## 📂 Repository Structure

```text
├── Rome_Forecasting_Weather_ENSO_final.ipynb   # Main Jupyter Notebook containing analysis & code
├── Report.pdf                                  # Detailed project report and findings
├── Slides.pdf                                  # Presentation slides
├── Roma_weather_noaa_full_months_filled.csv    # Cleaned dataset (NOAA daily data aggregated)
├── Roma_weather_noaa_with_ENSO.csv             # Dataset augmented with ENSO indices
├── nina34.anom.csv                             # Raw ENSO anomaly data
├── results_full/                               # Generated models, plots, and tables
│   ├── models/                                 # Saved .joblib model files
│   ├── plots/                                  # PNG exports of forecast plots
│   └── tables/                                 # CSV exports of metrics
└── README.md                                   # Project documentation

📊 Dataset
The primary data comes from the ROMA CIAMPINO meteorological station (ID: IT000016239).

Time Range: 1951-01 to 2022-09

Target Variable: TAVG (Monthly Average Temperature in °C)

Exogenous Variables:

PRCP: Monthly Total Precipitation

ENSO Index: Oceanic Niño Index (ONI) / Niño 3.4 SST anomalies (Climate driver)

Fourier Terms: Deterministic seasonality features

Data processing includes filling missing months using NOAA daily data aggregations to ensure a continuous timeline.

🧠 Methodology & Models
The project utilizes the Box-Jenkins methodology for model building:

Pre-processing: Stationarity checks (ADF, KPSS tests) and seasonal decomposition.

Models Implemented:

SARIMA: Baseline univariate Seasonal ARIMA.

SARIMAX (Precipitation): Incorporating rainfall as an exogenous regressor.

SARIMAX (Fourier): Modeling seasonality with Fourier series.

SARIMAX (ENSO): Testing the predictive power of the El Niño signal.

Evaluation: Models are compared using AIC/BIC criteria and forecast accuracy metrics (RMSE, MAE) on the test set.

🚀 How to Run the Code
Prerequisites

Ensure you have Python installed with the following libraries:

pandas

numpy

matplotlib

seaborn

statsmodels

pmdarima

joblib

scipy

Installation

You can install the dependencies via pip:

Bash
pip install pandas numpy matplotlib seaborn statsmodels pmdarima joblib scipy
Execution

Clone this repository:

Bash
git clone [https://github.com/BalerionIT/Rome_Forecasting_Weather.git](https://github.com/BalerionIT/Rome_Forecasting_Weather.git)
Open the Jupyter Notebook:

Bash
jupyter notebook Rome_Forecasting_Weather_ENSO_final.ipynb
Run all cells to reproduce the analysis, model training, and plots.

📈 Results Highlights
The analysis confirms a clear warming trend in Rome over the last 70 years.

SARIMAX models incorporating specific covariates were compared against the baseline SARIMA.

The final 10-year forecast provides insights into potential future temperature anomalies. (For detailed metrics and plots, please refer to the Report.pdf included in this repo.)
