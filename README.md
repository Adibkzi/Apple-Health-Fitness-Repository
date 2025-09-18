# 📊 Apple Health Daily Prediction & Recommendations

This project uses **Apple Health daily data** (steps, sleep, heart rate, etc.) to build a simple **machine learning pipeline** that predicts whether you’ll hit your step goal tomorrow, and gives **personalized recommendations** to improve your health.

---

## 🚀 Project Overview

- **Goal:** Predict if tomorrow’s steps ≥ 10,000 (or configurable `GOAL`)  
- **Tech:** Python, Pandas, Scikit-learn, Matplotlib  
- **Approach:**  
  1. Load daily Apple Health export (CSV)  
  2. Engineer features (rolling averages, lags, weekend indicator)  
  3. Create label (`hit_10k_tomorrow`)  
  4. Train logistic regression with class balancing  
  5. Tune decision threshold on validation slice  
  6. Evaluate on test set with **ROC-AUC, PR-AUC, F1**  
  7. Predict today’s probability of hitting goal tomorrow  
  8. Generate **recommendations** (e.g. sleep more, walk earlier)  

---

## 📂 Repository Structure

