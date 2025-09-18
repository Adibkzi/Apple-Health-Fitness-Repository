#  Apple Health Daily Prediction & Recommendations

> End-to-end data science project: process Apple Health daily data, forecast step-goal success for tomorrow, and deliver personalized wellness recommendations.

---

## 1️⃣ Project Goal

- Predict whether the user will reach **10,000 steps tomorrow** (or a configurable step goal).  
- Provide actionable recommendations (sleep earlier, walk in the morning, hydrate) based on recent trends in activity, sleep, and resting heart rate.  
- Build an interpretable, well-calibrated model with threshold tuning to balance precision and recall.

---

## 2️⃣ Data

- File(s): `Apple Health Dataset.csv` (example/simulated), or real Apple Health export processed into daily summary.  

- Derived features:  
  `steps_ma3` (3-day moving average steps), `sleep_ma3`, `rhr_ma3`, `steps_yday`, `is_weekend`, `active_energy_ma3`  

---

## 3️⃣ Workflow

1. **Data Loading & Cleaning**  
   - Read CSV, convert date column, sort chronologically.  
   - Check for missing values.  

2. **Feature Engineering**  
   - Rolling averages (3-day) for steps, sleep, resting HR.  
   - Lag features (yesterday’s steps), weekend indicator, optional energy feature.  

3. **Target Definition**  
   - Label `hit_10k_tomorrow`: whether next day’s steps ≥ goal.  

4. **Model Training & Threshold Tuning**  
   - Train a Logistic Regression with balanced class weights.  
   - Split data time-wise ensuring both classes present in test set.  
   - Tune decision threshold to maximize F1 score on validation slice.  

5. **Evaluation**  
   - Metrics: Accuracy, ROC-AUC, PR-AUC, F1, and confusion matrix.  

6. **Prediction & Recommendations**  
   - Compute probability for “tomorrow”.  
   - Based on low probability and feature thresholds, recommend specific actions (sleep earlier, walk in morning, reduce stress etc.).

---
🧑‍💻 **Author:** Adib Kazi — Passionate about turning data into healthy habits and insights.

