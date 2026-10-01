# 🌦️ Weather Intelligence & Smart Recommendation System

## 📌 Project Overview

This project is an end-to-end weather analytics system designed to collect frequently updated weather data, store historical observations/forecasts, perform data analysis, visualize weather trends, and generate actionable recommendations.

The project combines **Data Analytics, Business Intelligence, Automation, and Machine Learning**.

### Business Objective

The objective is to answer questions such as:

* What are the current weather conditions?
* How is the weather changing over time?
* Which cities have higher temperature, humidity, rainfall, or wind conditions?
* What weather conditions are expected in the coming hours?
* Can weather conditions trigger useful recommendations?
* How accurately can a machine learning model predict selected weather conditions?
* How accurate were previous forecasts?

---

# 🏗️ Project Architecture

```text
                 ┌──────────────────────┐
                 │   Open-Meteo API     │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ Python Data Pipeline │
                 │ Requests + Pandas    │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ Cleaning & Validation│
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   SQL Database       │
                 │ Historical Data      │
                 └───────┬───────┬──────┘
                         │       │
              ┌──────────┘       └───────────┐
              ▼                              ▼
     ┌──────────────────┐          ┌──────────────────┐
     │ Python Analytics │          │ Machine Learning │
     └────────┬─────────┘          └────────┬─────────┘
              │                             │
              └──────────────┬──────────────┘
                             ▼
                  ┌──────────────────────┐
                  │ Recommendations     │
                  └──────────┬───────────┘
                             │
                 ┌───────────┴───────────┐
                 ▼                       ▼
        ┌────────────────┐       ┌────────────────┐
        │   Power BI     │       │   Streamlit    │
        │   Dashboard    │       │   Web App      │
        └────────────────┘       └────────────────┘
```

---

# 📡 Data Source

The project uses the **Open-Meteo Weather API**.

Data collected includes:

* Temperature
* Relative humidity
* Dew point
* Precipitation
* Precipitation probability
* Wind speed
* Wind gusts
* UV index
* Visibility
* Forecast timestamps

The API is queried periodically to maintain updated weather information and historical forecast snapshots.

---

# ⚙️ Technology Stack

| Technology   | Purpose                        |
| ------------ | ------------------------------ |
| Python       | Data collection and processing |
| Requests     | API requests                   |
| Pandas       | Data cleaning and analysis     |
| SQL / SQLite | Data storage and querying      |
| Power BI     | Business dashboard             |
| Streamlit    | Interactive web application    |
| Plotly       | Interactive visualizations     |
| Scikit-learn | Machine learning               |
| Git / GitHub | Version control                |

---

# 📊 Data Pipeline

The pipeline follows these steps:

```text
API
 ↓
Data Collection
 ↓
Validation
 ↓
Cleaning
 ↓
Transformation
 ↓
SQL Storage
 ↓
EDA & Analytics
 ↓
Visualization
 ↓
Recommendation
 ↓
Machine Learning
```

The collection process is designed to run periodically, approximately every 15–60 minutes depending on the deployment configuration and API requirements.

---

# 📈 Analytics

The project analyzes:

### Temperature

* Current temperature
* Average temperature
* Maximum temperature
* Minimum temperature
* Temperature trends

### Humidity

* Average humidity
* Humidity trends
* Temperature vs humidity relationship

### Rainfall

* Precipitation
* Probability of precipitation
* Rainfall trends

### Wind

* Wind speed
* Maximum wind speed
* Wind trend

### City Comparison

Cities can be compared using:

* Temperature
* Humidity
* Rainfall
* Wind
* UV index

---

# 🤖 Recommendation System

The system uses two recommendation approaches.

## 1. Rule-Based Recommendations

Examples:

```text
IF precipitation probability is high
→ Recommend carrying an umbrella.

IF UV index is high
→ Recommend sun protection.

IF wind speed exceeds configured threshold
→ Display wind caution.

IF air quality exceeds configured threshold
→ Display air-quality caution.
```

Each recommendation includes the condition that triggered it so that the result remains explainable.

## 2. Machine Learning

A machine learning model is used for a selected prediction task such as:

* Next-hour temperature prediction
* Probability of measurable precipitation

Candidate models include:

* Linear Regression
* Logistic Regression
* Random Forest

Model performance is evaluated using appropriate time-based validation.

---

# 📊 Machine Learning Evaluation

For regression:

* MAE
* RMSE
* R²

For classification:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC where appropriate

A simple baseline model is also used for comparison.

---

# 📊 Power BI Dashboard

The Power BI report contains:

### Page 1 — Weather Overview

* Current temperature
* Humidity
* Wind speed
* Precipitation probability
* Last data update
* Selected city

### Page 2 — Weather Trends

* Temperature trend
* Humidity trend
* Rainfall trend
* Wind trend

### Page 3 — City Comparison

* Temperature comparison
* Humidity comparison
* Rainfall comparison
* Wind comparison

### Page 4 — Prediction & Recommendation

* Actual vs predicted values
* Model metrics
* Recommendation summary
* Weather alerts

---

# 🌐 Streamlit Application

The Streamlit application provides:

* City selection
* Latest weather conditions
* Forecast visualization
* Historical trends
* Interactive charts
* Rule-based recommendations
* ML predictions
* Model performance

---

# 🗄️ Database Design

The historical weather table contains fields such as:

```text
city
latitude
longitude
forecast_for
fetched_at
temperature
humidity
dew_point
precipitation
precipitation_probability
wind_speed
wind_gust
uv_index
visibility
```

Two timestamps are important:

* `forecast_for` — the time the weather value refers to
* `fetched_at` — the time the API response was collected

Keeping both allows forecast accuracy to be evaluated later.

---

# 🔍 Key Business Questions

The project answers questions such as:

1. Which city currently has the highest temperature?
2. How has temperature changed during the last 24 hours?
3. Which locations have the highest precipitation probability?
4. How does humidity change with temperature?
5. Which weather conditions trigger recommendations?
6. How accurate is the ML prediction?
7. How accurate were previous forecasts?
8. Which cities show unusual weather changes?

---

# 🚀 Installation

Clone the repository:

```bash
git clone <your-github-repository-url>
cd weather-analytics
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the Streamlit application:

```bash
streamlit run app/streamlit_app.py
```

---

# 📁 Project Structure

```text
weather-analytics/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
├── notebooks/
├── src/
├── app/
├── powerbi/
├── models/
└── tests/
```

---

# 🎯 Future Improvements

* Automated cloud deployment
* More cities
* Weather anomaly detection
* Improved forecasting models
* Automated email notifications
* Scheduled data pipeline
* PostgreSQL database
* Docker deployment
* Cloud-based data pipeline

---

# 👨‍💻 Skills Demonstrated

This project demonstrates:

* REST API integration
* Automated data collection
* Data cleaning
* Exploratory Data Analysis
* SQL
* Python
* Pandas
* Data visualization
* Power BI
* Streamlit
* Machine Learning
* Time-series analysis
* Recommendation systems
* Git/GitHub
* End-to-end data pipeline development

---

# 📌 Project Status

**Current Stage:** Development

The project is being developed incrementally, beginning with API-based weather data collection and expanding into historical analytics, dashboards, recommendations, and machine learning.

---

# 📄 Data Source

Weather data is provided by Open-Meteo.

Source: https://open-meteo.com/

Please review the provider's current terms, usage limits, and attribution requirements before deployment.
