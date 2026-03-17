# Divvy Station Demand Analysis & Forecasting
### Time-Series Modeling and Operational Insights for Streeter Dr & Grand Ave Station (Chicago)

## 📌 Project Overview

This project analyzes ride demand patterns at the Streeter Dr & Grand Ave Divvy station in Chicago using 2023–2024 trip and weather data.

The objective is to understand temporal usage trends, rider behavior differences, and environmental influences on bike demand, and to build forecasting models for operational planning and resource optimization.

---

## 🎯 Business Objective

The Streeter Dr & Grand Ave station experiences:

- Morning bike shortages (net outflow)
- Evening dock congestion (net inflow)
- High seasonal demand spikes (summer tourism)
- Weather-sensitive casual ridership

This project aims to:

- Identify demand patterns  
- Quantify weather impact  
- Detect operational imbalances  
- Forecast future ride volume  

---

## 📊 Data Sources

- Chicago Divvy Trip Data (2023–2024)
- Open-Meteo API (Hourly Weather Data)

The dataset was filtered to analyze only rides starting at Streeter Dr & Grand Ave station.

---

## 🔍 Exploratory Data Analysis (EDA)

### 1️⃣ Temporal Usage Patterns
- Peak ridership between 2–3 PM
- Casual users dominate weekends and summer afternoons
- Members align with weekday commute hours
- Strong seasonal trend: Summer > Spring > Fall > Winter

### 2️⃣ Weather Impact
- Ride volume increases between 10–30°C
- Casual ridership drops significantly above 8 m/s wind speed
- Rain and snow reduce weekend ride activity sharply
- Members show relatively stable usage across weather conditions

### 3️⃣ Net Ride Flow Analysis
- Morning: Net bike outflow (risk of shortages)
- Evening: Net bike inflow (dock congestion)
- Afternoon: Balanced flow
- Insight: Time-based rebalancing required

### 4️⃣ Ride Duration vs Distance
- Members: Linear distance-duration relationship
- Casual users: More long-duration short-distance outliers
- Suggests leisure behavior and possible inefficiencies

---

## 🤖 Forecasting Models Implemented

### 🔹 Weighted Moving Average
- Weather-adjusted smoothing
- MSE: 18.89
- MAE: 2.29

### 🔹 SARIMA (1,1,1)(1,1,1,52)
- Captures weekly and yearly seasonality
- Interpretable forecasts with confidence bands

### 🔹 Recurrent Neural Network (RNN)
- 21-day lookback window
- MSE: 12.81
- MAE: 2.09
- Captures short-term trends

### 🔹 Long Short-Term Memory (LSTM) — Best Performing Model
- 10-day lookback window
- MSE: 13.32
- MAE: 2.04
- R² Score: 0.599
- Stronger temporal learning and generalization

LSTM demonstrated the best balance between trend capture and forecasting accuracy.

---

## 📈 Operational Recommendations

- **Time-Based Rebalancing:** Morning restocking and evening redistribution.
- **Weather-Aware Adjustments:** Use short-term forecasts to dynamically adjust supply.
- **Off-Peak Incentives:** Shift demand from peak hours using pricing strategies.
- **User Education:** Improve guidance for casual riders to reduce inefficient trips.
- **Forecast-Based Staffing:** Use LSTM/SARIMA forecasts for seasonal planning.

---

## 🛠️ Tech Stack

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Statsmodels (SARIMA)  
- TensorFlow / Keras (RNN, LSTM)  
- Open-Meteo API  

---

