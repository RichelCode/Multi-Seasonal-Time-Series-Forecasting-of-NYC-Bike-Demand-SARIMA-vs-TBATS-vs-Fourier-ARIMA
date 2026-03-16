# Multi-Seasonal Time Series Forecasting of NYC Bike Demand

## Overview

This project explores time series forecasting using real-world bike-sharing data from New York City's Citi Bike system. The goal is to model and predict hourly bike demand while addressing a key challenge in time series analysis: **multiple seasonal patterns**.

Many real-world datasets exhibit more than one seasonal cycle. In this case, bike demand follows both **daily commuting patterns** and **weekly behavioral patterns**. Traditional models such as SARIMA are limited to capturing only one seasonal component, which motivates the use of more advanced forecasting approaches.

This project compares single-seasonal and multi-seasonal models to evaluate their performance and limitations.

---

## Problem Statement

The objective of this project is to:

* Identify and analyze seasonal patterns in bike demand
* Evaluate SARIMA models using both manual identification and automatic selection
* Compare SARIMA with models designed for multiple seasonalities
* Assess forecasting performance using standard accuracy metrics

---

## Dataset

The dataset consists of trip-level records from the NYC Citi Bike system. Each record represents an individual bike trip, including the start time and other trip details.

For this project, trip data from:

* July 2025
* August 2025
* September 2025

was used.

The raw data was aggregated into **hourly trip counts**, transforming event-level data into a structured time series suitable for forecasting.

---

## Key Characteristics of the Data

The resulting time series exhibits two clear seasonal patterns:

* **Daily seasonality (24 hours)** — driven by commuting behavior
* **Weekly seasonality (168 hours)** — differences between weekdays and weekends

These multiple seasonal cycles make the dataset ideal for evaluating forecasting models.

---

## Methodology

The project follows a structured time series workflow:

### 1. Data Preprocessing

* Merged multiple monthly datasets
* Converted timestamps into hourly intervals
* Aggregated trips into hourly demand
* Ensured continuity by filling missing time points

### 2. Exploratory Data Analysis (EDA)

* Visualized the full time series
* Examined daily and weekly patterns
* Identified multiple seasonal structures

### 3. SARIMA Modeling

* Used ACF and PACF for manual model identification
* Fitted a manually specified SARIMA model
* Compared with an automatically selected SARIMA model
* Evaluated residual diagnostics

### 4. Multi-Seasonal Modeling

To address multiple seasonal patterns, the following models were implemented:

* Fourier terms + ARIMA errors
* TBATS (Trigonometric, Box-Cox, ARMA, Trend, Seasonal)
* Prophet (optional extension)

### 5. Model Evaluation

All models were evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Percentage Error (MAPE)

A consistent train-test split was used to ensure fair comparison.

---

## Results and Key Insights

* SARIMA models struggled to capture both daily and weekly patterns simultaneously
* Multi-seasonal models significantly improved forecasting accuracy
* Fourier-based models and TBATS were particularly effective in modeling complex seasonal structures
* The limitations of SARIMA were shown to be structural rather than due to parameter tuning

---

## Why This Project Matters

This project highlights an important real-world insight:

> Many time series in practice contain multiple seasonal cycles, and choosing the right model structure is critical for accurate forecasting.

Applications of this work include:

* Urban mobility planning
* Bike-sharing system optimization
* Demand forecasting in transportation systems

---

## Tools and Libraries

* R
* forecast
* tseries
* ggplot2
* lubridate
* dplyr

---

## Project Structure

```
├── data/                  # Raw and processed data
├── scripts/               # R scripts for preprocessing and modeling
├── report/                # RMarkdown report
├── figures/               # Generated plots
├── README.md              # Project documentation
```

---

## Future Improvements

* Extend analysis to multiple years of data
* Incorporate external variables (weather, holidays)
* Explore deep learning models such as LSTM or Graph Neural Networks

---

## Author

Richel Attafuah

This project is part of a broader journey to make machine learning and data science concepts intuitive, practical, and accessible.
