AirLens — Pakistan Air Quality Analysis Dashboard
A multi-page interactive web dashboard that applies statistical and probabilistic analysis on real hourly air quality data collected from Pakistani cities.

🔍 Overview
Air pollution is one of Pakistan's most pressing environmental challenges. AirLens tackles this by transforming raw sensor data into meaningful statistical insights through an interactive dashboard.
The app processes ~21,840 hourly readings across multiple Pakistani cities, covering pollutants like PM2.5, PM10, NO2, CO, and O3 alongside weather variables like temperature, humidity, and wind speed. Every page applies a different statistical concept — from descriptive summaries to regression modeling — making this both a functional tool and a demonstration of applied probability and statistics.

✨ Features
🏠 Dashboard
A city-wide overview showing real-time AQI status, active filters, and key dataset metrics at a glance.
📊 Charts
Interactive time-series plots for each pollutant with city and date range filters. Spot seasonal trends and pollution spikes visually.
📈 Statistics
Computes mean, median, mode, standard deviation, variance, skewness, kurtosis, and 95% confidence intervals for each pollutant per city. Automatically classifies distributions as symmetric, right-skewed, or left-skewed and overlays normal curves on histograms.
🎲 Probability & Risk
Fits a normal distribution to each pollutant using Maximum Likelihood Estimation. Generates PDF and CDF curves and produces a city-wise risk table showing:

P(pollutant > 150) : Unhealthy threshold
P(pollutant > 200) : Very unhealthy threshold
P(pollutant < 50)  : Safe zone probability

Also includes Q-Q plots and a Chi-Square goodness-of-fit test to validate whether data follows a normal distribution.
🤖 Regression & Prediction
Builds two models:

Simple OLS — PM2.5 → AQI with regression line
Multivariate OLS — PM2.5, NO2, CO → AQI

Reports R², RMSE, and MAE. Visualizes residuals and error distribution to check model assumptions. Includes a live forecast tool — adjust PM2.5, NO2, and CO sliders to get an instant AQI prediction with color-coded health status.
🔗 Correlation Analysis
A Pearson correlation heatmap across AQI, PM2.5, PM10, NO2, CO, and O3. Automatically surfaces the strongest pollutant pairs and labels them as critical (r > 0.85), strong (r > 0.6), or moderate.

🗃️ Dataset
PropertyDetailFilepakistan_air_quality_final_clean.csvRecords~21,840 hourly readingsCitiesFaisalabad + multiple Pakistani citiesPollutantsPM2.5, PM10, CO, NO2, SO2, O3, DustWeather FeaturesTemperature, humidity, wind speed, pressure, seasonAQI CalculationUS EPA PM2.5 breakpoint formula (implemented in data_loader.py)

🛠️ Tech Stack
ToolPurposePython 3.10+Core languageStreamlitWeb application frameworkPandas / NumPyData processing and computationSciPyDistribution fitting, hypothesis testing, confidence intervalsScikit-learnOLS regression and model evaluationPlotlyAll interactive charts and heatmaps

📁 Project Structure
AirLens/
├── app.py                 # Main app — navigation, sidebar filters, global CSS
├── data_loader.py         # Data loading, column mapping, AQI calculation
├── page_dashboard.py      # Overview page
├── page_charts.py         # Time-series charts
├── page_statistics.py     # Descriptive statistics + distribution analysis
├── page_probability.py    # PDF, CDF, risk tables, Q-Q plots, Chi-Square
├── page_regression.py     # OLS regression + live forecast tool
├── page_correlation.py    # Pearson heatmap + association findings
└── pakistan_air_quality_final_clean.csv

🚀 Getting Started
bash# Clone the repository
git clone https://github.com/ZainabKhurram08/AirLens.git
cd AirLens

# Install dependencies
pip install streamlit pandas numpy scipy scikit-learn plotly

# Run the app
streamlit run app.py

📐 Statistical Concepts Applied

Grouped descriptive statistics (mean, median, mode, variance, std dev)
Normal distribution fitting via Maximum Likelihood Estimation
PDF and CDF curve generation
Risk probability computation using the normal CDF
Q-Q plots for visual normality assessment
Chi-Square goodness-of-fit test
95% Confidence Intervals using t-distribution
Skewness and Kurtosis interpretation
Simple and Multivariate OLS Regression
Residual analysis and error distribution
Pearson Correlation Matrix
