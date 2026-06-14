# 🌫️ AirLens — Pakistan Air Quality Analysis Dashboard

**A multi-page interactive web dashboard that applies statistical and probabilistic analysis on real hourly air quality data collected from Pakistani cities.**

---

## 🔍 Overview

Air pollution is one of Pakistan's most pressing environmental challenges. **AirLens** tackles this by transforming raw sensor data into meaningful statistical insights through an interactive dashboard.

The app processes **~21,840 hourly readings** across multiple Pakistani cities, covering pollutants like PM2.5, PM10, NO2, CO, and O3 alongside weather variables like temperature, humidity, and wind speed. Every page applies a different statistical concept  from descriptive summaries to regression modeling making this both a functional tool and a demonstration of applied probability and statistics.

---

## ✨ Features

### 🏠 Dashboard
A city-wide overview showing real-time AQI status, active filters, and key dataset metrics at a glance.

### 📊 Charts
Interactive time-series plots for each pollutant with city and date range filters. Spot seasonal trends and pollution spikes visually.

### 📈 Statistics
Computes **mean, median, mode, standard deviation, variance, skewness, kurtosis**, and **95% confidence intervals** for each pollutant per city. Automatically classifies distributions as symmetric, right-skewed, or left-skewed and overlays normal curves on histograms.

### 🎲 Probability & Risk
Fits a normal distribution to each pollutant using **Maximum Likelihood Estimation**. Generates **PDF and CDF curves** and produces a city-wise risk table showing:
- P(pollutant > 150)  Unhealthy threshold
- P(pollutant > 200)  Very unhealthy threshold
- P(pollutant < 50)   Safe zone probability

Also includes **Q-Q plots** and a **Chi-Square goodness-of-fit test** to validate whether data follows a normal distribution.

### 🤖 Regression & Prediction
Builds two models:
- **Simple OLS**  PM2.5 → AQI with regression line
- **Multivariate OLS**  PM2.5, NO2, CO → AQI

Reports **R², RMSE, and MAE**. Includes a **live forecast tool**  adjust sliders to get an instant AQI prediction with color-coded health status.

### 🔗 Correlation Analysis
A **Pearson correlation heatmap** across AQI, PM2.5, PM10, NO2, CO, and O3. Automatically labels pollutant pairs as critical (r > 0.85), strong (r > 0.6), or moderate.

---

## 🗃️ Dataset

| Property | Detail |
|---|---|
| **File** | `pakistan_air_quality_final_clean.csv` |
| **Records** | ~21,840 hourly readings |
| **Cities** | Faisalabad + multiple Pakistani cities |
| **Pollutants** | PM2.5, PM10, CO, NO2, SO2, O3, Dust |
| **Weather Features** | Temperature, humidity, wind speed, pressure, season |
| **AQI Calculation** | US EPA PM2.5 breakpoint formula |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.10+** | Core language |
| **Streamlit** | Web application framework |
| **Pandas / NumPy** | Data processing and computation |
| **SciPy** | Distribution fitting, hypothesis testing, confidence intervals |
| **Scikit-learn** | OLS regression and model evaluation |
| **Plotly** | All interactive charts and heatmaps |

---

## 🚀 Getting Started

```bash
git clone https://github.com/ZainabKhurram08/AirLens.git
cd AirLens
pip install streamlit pandas numpy scipy scikit-learn plotly
streamlit run app.py
```

---

## 📐 Statistical Concepts Applied

- Grouped descriptive statistics (mean, median, mode, variance, std dev)
- Normal distribution fitting via Maximum Likelihood Estimation
- PDF and CDF curve generation
- Risk probability computation using the normal CDF
- Q-Q plots for visual normality assessment
- Chi-Square goodness-of-fit test
- 95% Confidence Intervals using t-distribution
- Skewness and Kurtosis interpretation
- Simple and Multivariate OLS Regression
- Residual analysis and error distribution
- Pearson Correlation Matrix

---
