# Spatio-Temporal Prediction of Temperature–Humidity Index (THI) in Kerala
Author: Ashwathy Nair
Supervisor: Dr. Radhakrishnan T
Program: M.Sc. Data Analytics and Geoinformatics, Digital University Kerala



## Overview
This project explores heat stress in cattle caused by rising Temperature–Humidity Index (THI) levels across Kerala. With geospatial data and deep learning models, the study predicts spatio-temporal variations in THI to support data-driven mitigation strategies for the dairy sector.

## Aim & Objectives
Aim:
To analyze, model, and predict THI variations in Kerala using geospatial and deep learning techniques.

Objectives:
-Compile open-source temperature and humidity data (ERA5-Land, 2013–2024)
-Analyze spatial and temporal variations of THI
-Develop and compare forecasting models — SARIMA, LSTM, ConvLSTM
-Evaluate model performance and validate predictions
-Provide actionable insights for localized heat-stress mitigation

## Study Area
Kerala, India

## Data & Sources
Source - ERA5-Land (ECMWF)
Type - Reanalysis (Temperature & Humidity)
Spatial Resolution - 0.1° (~11 km)
Temporal Coverage - 2013–2024
Format - NetCDF

## Methodology
### Pre-processing:
-Extracted Kerala subset from global ERA5-Land data and merged data for the entire study period
-Handled NaNs
-Calculated THI for each day across the study period(2013–2024)
### Exploratory Data Analysis (EDA)
-Identified hottest/coolest periods
-Seasonal-trend decomposition (STL)
-Temporal autocorrelation (ACF/PACF)
### Modelling Approaches
-SARIMA (Per-point): Baseline temporal model for each spatial pixel
-LSTM (Per-point): Sequence-based model (10-day lookback → 5-day forecast)
-ConvLSTM (Grid-based): Spatio-temporal deep learning model preserving spatial context
### Spatial Analysis
-Moran’s I: Measure of spatial autocorrelation for the residuals of SARIMA (which showed visual spatial relationship)
-K-Means Clustering: THI zone classification (Initial THI visualization showed strong clustering patterns)

### Model Performance
Performance metrics of different models for THI forecasting

Model	            MAE	    MSE	    RMSE	  R2
Per-Point SARIMA	1.3195	2.6385	1.6244	0.8185
Per-Point LSTM	  1.4113	3.2190	1.7941	0.8348
ConvLSTM	        1.1106	2.2742	1.5080	0.8577

## Key Findings
-Midlands show the highest THI, especially during April–May.
-Highlands remain cooler due to elevation.
-Coastal zones show moderate THI due to sea-breeze effects.
-Post-monsoon (July–Aug) period shows lowest THI.
-ConvLSTM effectively preserves spatial and temporal coherence.

<img width="1022" height="610" alt="image" src="https://github.com/user-attachments/assets/ca150355-48c5-4ec9-b6c8-f90367f89148" />




