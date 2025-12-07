#Chicago Traffic Accidents Analysis and Predictive Modeling

#Overview

This repository contains a full data science workflow for analyzing the Chicago Traffic Crash Dataset and building predictive models to identify the primary contributory causes of accidents. The project demonstrates end‑to‑end processing including data cleaning, exploratory data analysis (EDA), feature engineering, geospatial analysis, class balancing, modeling, and evaluation.

The final deliverable is a multi-class classification pipeline aimed at helping transportation authorities and safety planners transition from reactive accident reporting to proactive accident prevention.

---

#Project Objectives

#Main Objective

Develop a machine learning model capable of predicting the primary contributory cause category of a traffic crash.

#Specific Objectives

· Analyze the effect of weather, lighting, road defects, crash type, and speed limits on crash occurrence.
· Identify yearly, monthly, weekly, and hourly crash trends.
· Determine high-risk locations and hotspots using geospatial clustering.
· Investigate relationships between crash severity, number of vehicles involved, and contributory causes.
· Build and evaluate supervised learning models for classification.

---

#Dataset

· Source: Chicago Data Portal – Traffic Crashes (Vehicles)
· Size: ~993,000 records
· Columns: 48 original features → reduced after cleaning

#Key Fields Used

· crash_date
· posted_speed_limit
· weather_condition
· lighting_condition
· road_defect
· first_crash_type
· trafficway_type
· injuries_total
· most_severe_injury
· latitude, longitude
· prim_contributory_cause → mapped to Cause_Group

---

#Data Preparation

#Steps

1. Removal of high-missing-value features
2. Dropping irrelevant administrative fields
3. Standardization of labels and whitespace removal
4. Datetime conversion and feature extraction (hour, day, month)
5. Handling missing values
6. Class mapping into 7 "Cause_Group" categories
7. Outlier inspection and retention of real-world extreme values
8. Encoding categorical features using LabelEncoder

---

#Feature Engineering

#Primary Contributory Cause Grouping

Over 40 original labels were consolidated into 7 interpretable groups:

· Speed & Right‑of‑Way Failure
· Maneuver & Positioning Error
· Disregard Traffic Controls
· Impairment & Recklessness
· Distraction & Visibility
· External/Environmental/Mechanical
· Unclassified/Administrative

#Additional Engineered Features

· crash_hour
· crash_day_of_week
· crash_month
· Location_Key

---

#Exploratory Data Analysis (EDA)

#Analyses Included

· Injury severity distribution
· Top contributing causes
· Crash trends by year
· Peak crash hours, days, and months
· KDE distributions for numerical features
· Heatmaps for hour-by-day interactions
· Word Cloud for cause text frequency
· Hotspot detection using latitude/longitude

#Insights

· Most crashes occur at 30 mph, involve two vehicles, and result in no injuries.
· Clear weather and daylight record the highest incidents due to high traffic volume.
· Fridays record the most accidents; September is the peak month.
· Crash hotspots cluster around major intersections and dense traffic zones.

---

#Modeling

Target

Cause_Group (multi-class classification)

#Models Trained

· Decision Tree Classifier
· Random Forest Classifier
· Logistic Regression
· Gradient Boosting
· XGBoost (recommended for best performance)

#Class Balancing

Applied RandomOverSampler to address class imbalance.

#Evaluation Metrics

· Accuracy
· Precision, Recall, F1 Score
· Confusion Matrix
· ROC Curves
· Cross‑validation scores

#Key Results

· Baseline Decision Tree accuracy ~51%
· Random Forest accuracy ~51%
· XGBoost achieved superior consistency across minority classes

---

#Folder Structure

```
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
```

---

#How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/bryscax/chicago-traffic-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter notebooks or execute individual Python scripts in src/.

---

#Requirements

· Python 3.8+
· pandas, numpy
· seaborn, matplotlib
· scikit-learn
· xgboost
· imbalanced-learn
· plotly
· geopy
· wordcloud

---

#Key Deliverables

· Cleaned and structured dataset
· Complete EDA report with visualizations
· Feature engineering pipeline
· Predictive models with evaluation reports
· Geospatial hotspot mapping
· Final decision-support insights for traffic safety planning

---

#Authors

· Clariss Wangari Wathiai
· Leslie Nungi
· Mutuku Cyrus
· Grace Kinyanjui
· Bryan Caxton Njogu

GitHub: https://github.com/KareeClariss/Phase-4-Project.git

---

License

This project is released under the MIT License.
