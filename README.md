# Hospitality Dynamic Pricing & Customer Retention Analysis

## Executive Summary
In the highly competitive travel and hospitality sector, revenue leakage occurs due to unoptimized pricing and unpredictable customer cancellations (churn). This project analyzes a comprehensive hotel booking dataset to uncover the primary drivers of cancellations and explore seasonal pricing elasticity. The goal is to provide the data foundation for a dynamic pricing engine and targeted retention campaigns, ultimately optimizing Revenue Per Available Room (RevPAR).

## Business Objectives
* **Revenue Management:** Identify seasonal demand curves and Average Daily Rate (ADR) fluctuations to optimize room pricing dynamically.
* **Marketing Strategy:** Segment customers based on cancellation probability to deploy targeted promotional ad spend.
* **Predictive Intelligence:** Establish a baseline machine learning pipeline to predict whether a specific booking will be canceled before the arrival date.

## Technology Stack
* **Language:** Python 3
* **Data Processing & Engineering:** Pandas, NumPy
* **EDA & Statistical Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Logistic Regression, StandardScaler)
* **Business Intelligence:** Microsoft Power BI (using exported aggregations)

## Project Roadmap (4-Week Implementation)

### Week 1: Data Engineering & Cleaning
* Ingested historical booking records.
* Handled missing categorical data (e.g., agent/company IDs).
* Removed extreme pricing anomalies to normalize the Average Daily Rate (ADR).
* Engineered new features: `total_duration_of_stay` and `total_guests`.

### Week 2: Exploratory Data Analysis (EDA)
* Analyzed the overall churn metric (cancellation rate).
* Mapped the "Booking Curve" to visualize the relationship between Lead Time and cancellation volume.
* Generated a correlation matrix to identify the statistical significance of numerical features against the `is_canceled` target variable.

### Week 3: Baseline Predictive Modeling
* Deployed a **Logistic Regression** classification model to predict booking cancellations.
* Preprocessed data using One-Hot Encoding for categorical variables and Standard Scaling for numerical variables to prevent data leakage.
* Evaluated model performance using Accuracy, Precision, Recall, Confusion Matrices, and ROC-AUC curves.

### Week 4: Business Intelligence Integration
* Aggregated and exported two highly specialized datasets for Power BI integration:
  1. `bi_seasonal_pricing.csv` - Tailored for the Revenue Management team to visualize historical ADR peaks.
  2. `bi_segment_churn.csv` - Tailored for the Marketing team to identify high-risk customer segments.

## Strategic Recommendations
Based on the data analysis and predictive model, the following business actions are recommended:
1. **Dynamic Deposit Policies:** The model indicates a strong correlation between long lead times and cancellations. The hotel should implement scaled deposit requirements for bookings made more than 60 days in advance.
2. **Targeted Overbooking:** By utilizing the churn prediction model's outputs, the revenue team can confidently overbook inventory during historically high-cancellation periods without risking "walk-outs."
3. **Marketing Interventions:** The Marketing Director should utilize the segment analysis to send automated, personalized retention offers (e.g., room upgrades or dining credits) to high-risk customers 14 days prior to arrival.
