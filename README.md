# 🌊 El Niño Sea Surface Temperature Modeling

**Author:** Advay Kadam (`advayk2`)  
**Course:** STAT 429  
**Date:** March 28, 2025

## 📌 Motivation

El Niño and La Niña are large-scale climate patterns that originate in the Pacific Ocean and significantly influence global weather conditions. El Niño, in particular, affects the central and eastern tropical Pacific and is associated with increased hurricane activity in those regions. The historically intense El Niño of 1982–1983 raises key scientific questions:

- Can we effectively **predict the sea surface temperatures (SSTs)** during an El Niño cycle?
- Which **meteorological variables** are most significant in driving SST changes?

This project seeks to answer these questions through statistical modeling and time series analysis.

---

## 🧭 Objectives

- Predict **Average Sea Surface Temperature** using regression models.
- Identify the **most significant explanatory variables** contributing to SST.
- Compare model performance using **AIC**, **BIC**, **F-tests**, and **residual analysis**.

---

## 📈 Dataset Description

- **Time Span:** March 7, 1980 – June 10, 1998  
- **Observations:** Originally 178,080 entries → Aggregated to 6,371 daily averages  
- **Source:** [Kaggle](https://www.kaggle.com/datasets), originally from the **UCI Machine Learning Repository**  
- **Collection System:** Tropical Atmosphere Ocean (TAO) Array – a network of 70 buoys across the equatorial Pacific measuring:
  - Wind velocities
  - Humidity
  - Air and sea temperatures
  - Deep ocean pressure and temperature (up to 500m)

To reduce noise and redundancy, the dataset is aggregated by averaging all measurements for each day across different locations.

---

## 🧾 Columns

| Column             | Description |
|--------------------|-------------|
| `Obs`              | Observation index |
| `Year`             | Year (two-digit) |
| `Month`            | Month (1–12) |
| `Day`              | Day (1–31) |
| `Date`             | Concatenated Year-Month-Day |
| `Latitude`         | Geographic latitude |
| `Longitude`        | Geographic longitude |
| `Zonal.Winds`      | East-west wind velocity (m/s) |
| `Meridional.Winds` | North-south wind velocity (m/s) |
| `Humidity`         | Relative humidity (%) |
| `Air.Temp`         | Air temperature (°C) |
| `Sea.Surface.Temp` | Sea surface temperature (°C) |

---

## 📊 Visualization

A sample time series plot of **Average Sea Surface Temperature (°C)** over time reveals a **non-stationary series** with potentially heteroscedastic variance.

> _Plot to be included here (e.g., `plots/sst_vs_time.png`)_

---

## 🔍 Key Questions

1. Can we use **linear regression** to effectively predict SST?
2. Which variables (Humidity, Air Temp, Zonal/Meridional Winds, etc.) are **significant predictors**?
3. Which model performs best based on:
   - **Residual diagnostics**
   - **AIC/BIC**
   - **F-statistics**

---

## 🔬 Plan for Analysis

### Step A: Data Transformation
- Apply **variance-stabilizing transformations** (e.g., power transform).
- Use **differencing** to address non-stationarity.
- Note: Since variance appears to **decrease over time**, log transformation may not be appropriate.

### Step B: Model Fitting
- Explore **linear regression models** using various combinations of:
  - Time trends
  - Humidity
  - Air temperature
  - Zonal and Meridional wind speeds

### Step C: Model Evaluation
- **Residual plots**: histogram, ACF of residuals
- **Significance testing** using F-tests
- **Model comparison** via AIC and BIC

---

## 🛠️ Tools

- R
- Visualization: `ggplot2`, base R plotting
- Time Series Analysis: `forecast`, `astsa`

---

