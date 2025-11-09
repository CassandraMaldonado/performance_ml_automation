# Performance ML Automation

This project explores how manual machine learning pipelines compare to AutoML frameworks in predicting athletic performance outcomes.  
It demonstrates how feature engineering, hyperparameter tuning and automation can be combined to improve both accuracy and model efficiency.

## Project Overview

The goal of this project is to predict total lift performance for athletes using body metrics such as snatch, clean and jerk, body weight and height.  
Two complementary approaches were implemented and compared:

| Approach | Platform | Code Type | Goal |
|-----------|-----------|------------|------|
| **Manual ML** | Jupyter + Scikit-learn | Full-code | Build, tune and interpret models manually. |
| **AutoML** | AWS SageMaker | Low-code | Automatically find the best-performing model. |

## Manual ML Approach

**Steps:**
1. Data cleaning and feature engineering.
2. Training multiple regression models.
3. Manual hyperparameter tuning with GridSearchCV.  
4. Evaluation using R², RMSE and runtime.  

**Best Model:**  
- **Random Forest (Experiment 3)**  
- **R²:** 0.9997  
- **RMSE:** 5.10 
- **Training Time:** 64.2 seconds

## AutoML Approach (SageMaker)

**Steps:**
1. Loaded the cleaned dataset.
2. Ran AutoML for regression task.
3. Analyzed feature importance.
4. Identified top models by validation score and speed.
5. Compared AutoML vs manual ML.

**AutoML Results:**
- **Top 5 Features:** BodyWeight, Snatch, CleanAndJerk, Height, Age.
- **Top Model (All Features):** XGBoost  
- **Top Model (Top 3 Features):** CatBoost  
- **R²:** 0.9990  
- **RMSE:** 10.00  
- **Training Time:** 120 seconds  

**Platform Type:** Low-code (model training and evaluation via UI, minimal coding)

---

## 📊 **Comparison Summary**

| Metric | Manual (Random Forest) | AutoML (XGBoost) |
|---------|------------------------|------------------|
| R² | 0.9997 | 0.9990 |
| RMSE | 5.10 | 10.00 |
| Training Time (s) | 64.2 | 120.0 |
| Control | Full | Limited |
| Code Type | Full-code | Low-code |

**Key Insight:**  
Manual tuning achieved slightly higher accuracy and faster runtime.  
AutoML, however, provided strong performance with minimal setup and faster experimentation cycles.

---
