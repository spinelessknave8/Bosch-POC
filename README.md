# Bosch-POC
## Overview
The goal of this project is to explore how **non-personal data collected from home appliances** — specifically microwave usage logs — can be modeled to uncover user preferences, improve prediction outcomes, and derive actionable insights. This includes:

- Researching and analyzing usage data to identify patterns
- Testing machine learning algorithms suitable for non-personal data
- Evaluating baseline models and data fusion techniques
- Presenting findings that support product enhancement and business optimization


The dataset used is sourced from Kaggle and contains microwave usage logs.

## Dataset
Microwave Usage Dataset: https://www.kaggle.com/datasets/lgarg442/microwave-usage-data/data

## Analysis
1. **Data Cleaning & Preprocessing**
   - Dropped `User_ID` for privacy
   - Converted timestamps to extract `Hour`, `DayOfWeek`, and `Month`
   - Encoded categorical variables using OneHotEncoding and ordinal mapping

2. **Exploratory Data Analysis**
   - Visualized frequency of food types, modes, power levels, and usage times
   - Found that microwaves are most used at 1 AM and on Wednesdays
   - Chicken is the most microwaved food

3. **Statistical Testing**
   - Used **Kruskal-Wallis** tests to check if categorical features affect `Power_Consumed`
   - **Result**: No significant effect from `Food_Type`, `Mode_Selected`, `DayOfWeek`, etc.

4. **Machine Learning**
   - Models: **XGBoost** and **CatBoost**
   - Goal: Predict `Power_Consumed` using contextual features
   - **Result**: Poor performance (RMSE > 500, R² < 0), indicating weak predictive power

## Key Findings
- **Primary drivers of energy consumption** are `Duration_Seconds` and `Power_Level_Value`
- **Contextual features** (e.g., food type, time of day) do **not** meaningfully predict energy usage
- **Behavioral insights** can still be extracted for product design and user experience optimization

## Future Directions
- Collect richer and more diverse data from appliances
- Explore hybrid models combining behavioral and technical metrics
- Focus on **habit learning** and **smart tuning** rather than direct energy prediction
