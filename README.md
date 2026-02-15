# Mississippi River 7-Day Discharge Forecasting Using Machine Learning

## Project Overview

This project develops a 7-day ahead river discharge forecasting model for the Mississippi River using machine learning techniques. The goal is to predict downstream discharge using publicly available hydrological and meteorological data in order to support flood risk assessment and early warning analysis.

The study integrates river discharge records with climate variables and evaluates the performance of different machine learning models against a traditional baseline approach.

---

## Objectives

* Collect and preprocess hydrological and meteorological datasets
* Engineer time-aware features such as lagged discharge and rainfall accumulation
* Develop machine learning models for 7-day ahead discharge forecasting
* Compare model performance with a persistence (naive) baseline
* Interpret feature importance and analyze hydrological behavior

---

## Data Sources

* USGS river discharge data
* NASA POWER meteorological data

Time period: 1981 – Present
Temporal resolution: Daily

Meteorological variables used in the model:

* Precipitation (PRECTOT)
* Temperature (T2M)
* Relative Humidity (RH2M)
* Wind Speed (WS2M)
* Surface Pressure (PS)

---

## Methodology

### Data Preparation

Hydrological and meteorological datasets were aligned by date and cleaned to ensure consistency. Missing values were handled and time-series alignment was verified.

### Feature Engineering

The following features were created:

* 3-day rainfall accumulation
* 7-day rainfall accumulation
* 1-day and 3-day discharge lags at St. Louis
* 1-day and 3-day upstream discharge lags (Keokuk station)

### Target Definition

The model predicts river discharge 7 days ahead. This was formulated as a regression problem.

### Train-Test Strategy

A chronological 80/20 time-based split was used to prevent data leakage. No random shuffling was applied.

### Models Implemented

* Persistence baseline (naive forecast)
* Random Forest Regressor
* Gradient Boosting Regressor

### Evaluation Metrics

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

---

## Results

| Model                | RMSE (cfs) |
| -------------------- | ---------- |
| Persistence Baseline | 64,447     |
| Random Forest        | 66,003     |
| Gradient Boosting    | 61,764     |

The Gradient Boosting model achieved approximately 4–5% lower RMSE compared to the persistence baseline. This indicates that machine learning captures additional nonlinear relationships beyond simple discharge memory, although short-term river forecasting remains strongly influenced by temporal persistence.

---

## Key Observations

* River discharge exhibits strong temporal autocorrelation.
* Discharge lag features dominate short-term forecasting performance.
* Upstream flow significantly influences downstream discharge.
* Rainfall contributes to forecasting performance but plays a secondary role over short horizons.
* Extreme peak discharges tend to be slightly underestimated by ensemble models.
  
---

## Academic Context

This project was developed as part of a Problem-Based Learning (PBL) academic initiative in engineering.

Project Guide:
Dr. Ashok Kumar Saini

---

## Author

Veer Aditya Mathuria
2427030360
B.Tech Engineering Project

