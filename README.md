**Chicago Traffic Accidents – Analysis & Predictive Modeling**
**Phase 4 Project – Group 13**
1. **Overview**

This project analyses nearly one million recorded traffic crashes in Chicago to identify the conditions and behaviours most strongly associated with accident occurrence and severity.
Using a complete data-science workflow—data cleaning, exploratory analysis, feature engineering, geospatial analytics, modelling, and evaluation—the project demonstrates how machine learning can support proactive road-safety planning.

The final output is a multi-class classifier that predicts the Cause Group of a crash, offering practical insights for transportation authorities.

**2. Project Objectives**
*Main Objective*

Build a supervised machine-learning model capable of predicting the Cause Group of a traffic crash.

**Supporting Objectives**

-Analyse how weather, lighting, road defects, speed limits, and crash type affect crash outcomes.

-Identify temporal accident patterns (year, month, week, hour).

-ap high-risk hotspots through geospatial clustering.

-Explore connections between injury severity, number of units, and contributory causes.

-Train and evaluate multiple classification algorithms.

**3. Dataset Description**

-Source: Chicago Data Portal – Traffic Crashes (Vehicles)
-Records: ~993,000
-Original Features: 48 → reduced and cleaned

**Key Variables Used**

**Crash characteristics:**
crash_date, posted_speed_limit, first_crash_type, trafficway_type

**Environmental conditions:**
weather_condition, lighting_condition, road_defect

**Severity indicators:**
injuries_total, most_severe_injury

**Location data:**
latitude, longitude, Location_Key

**Target variable:**
prim_contributory_cause → mapped into Cause_Group

**4. Data Preparation**

**Key steps included:**

-Removing irrelevant and high-missing features

-Standardising labels and correcting inconsistent text

-Converting datetime fields, extracting hour, day, month

-Mapping 40+ contributory-cause labels into 7 Cause Groups

-Checking outliers and retaining real-world extremes

-Encoding categorical variables using LabelEncoder

**5. Feature Engineering**
-Cause Group Consolidation

-The original contributory-cause categories were grouped into these seven interpretable classes:

-Speed & Right-of-Way Failure

-Maneuver & Positioning Error

-Disregard for Traffic Controls

-Impairment & Recklessness

-Distraction & Visibility

-Environmental / Mechanical

-Administrative / Unclassified

-Additional Engineered Features

-crash_hour

-crash_day_of_week

-crash_month

-Location_Key (intersection-level grouping)

**6. Exploratory Data Analysis (EDA)**
-Analyses Conducted

-Injury severity distribution

-Annual, monthly, weekly, and hourly crash trends

-Word cloud of contributory causes

-KDE distributions for numeric variables

-Heatmaps showing time-of-day patterns

-Crash hotspots using latitude/longitude clustering

**Key Findings**

-Most crashes involve two vehicles, occur at 30 mph, and result in no injuries.

-Clear weather and daylight have the most crashes due to higher traffic volumes.

-Fridays and the month of September show the highest crash activity.

-High-risk hotspots align with busy road junctions and major corridors.

**7. Modelling**
**Target Variable**

-Cause_Group (multi-class classification)

**Models Trained**

-Decision Tree

-Random Forest

-Logistic Regression

-Gradient Boosting

-XGBoost (top-performing model)

-Class Balancing Technique

-Applied RandomOverSampler to address target imbalance.

**Evaluation Metrics**

-Accuracy

-Precision, Recall, F1-score

-Confusion Matrix

-ROC-AUC curves for each class

-Cross-validation scoring

-Performance Summary

-Baseline Decision Tree accuracy: ~51%

-Random Forest accuracy: ~51%

-XGBoost provided the most stable performance, especially for minority classes.

**8. Project Structure**
├── data/
│   ├── traffic_crashes.zip
│   └── processed_data.csv
├── notebooks/
│   ├── eda.ipynb
│   ├── modelling.ipynb
│   └── geospatial_analysis.ipynb
├── src/
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   ├── model_training.py
│   └── visualization.py
├── outputs/
│   ├── figures/
│   └── models/
└── README.md

**9. How to Run the Project**
-Clone the repository
-git clone https://github.com/KareeClariss/Phase-4-Project.git

**Install dependencies**
**pip install -r requirements.txt**

**Run notebooks or scripts**

Open the notebooks in JupyterLab or execute Python scripts in src/.

***10. Requirements***

-Python 3.8+

-pandas, numpy

-matplotlib, seaborn

-scikit-learn

-xgboost

-imbalanced-learn

-plotly

-wordcloud

-geopy

**11. Authors**

-Clariss Wangari Wathiai

-Leslie Nungi

-Mutuku Cyrus

-Grace Kinyanjui

-Bryan Caxton Njogu

-Repository: https://github.com/KareeClariss/Phase-4-Project

***12. License***


Released under the MIT License.

