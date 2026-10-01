# weather-intelligence-analytics
Live weather analytics project using Python, SQL, Power BI, and Streamlit to collect, analyze, visualize, and predict weather data with actionable recommendations.
weather-analytics/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_api_data_collection.ipynb
│   ├── 02_data_cleaning_eda.ipynb
│   ├── 03_sql_analysis.ipynb
│   └── 04_ml_model.ipynb
│
├── src/
│   ├── api/
│   │   └── weather_api.py
│   │
│   ├── data/
│   │   ├── cleaning.py
│   │   └── validation.py
│   │
│   ├── database/
│   │   └── database.py
│   │
│   ├── analysis/
│   │   └── analytics.py
│   │
│   ├── recommendation/
│   │   ├── rules.py
│   │   └── ml_recommendation.py
│   │
│   └── ml/
│       ├── train.py
│       └── evaluate.py
│
├── app/
│   └── streamlit_app.py
│
├── powerbi/
│   └── weather_dashboard.pbix
│
├── models/
│   └── .gitkeep
│
└── tests/
    └── test_api.py
