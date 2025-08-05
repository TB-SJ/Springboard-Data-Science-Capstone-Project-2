# 🏒 NHL Goal Scoring Prediction Model

Predicting NHL player goal scoring potential for the upcoming season using machine learning.  
This model is designed to support contract negotiations, identify breakout players, and guide endorsement strategies by estimating a player’s goal-scoring likelihood.

---

## 📌 Table of Contents
- [Project Overview](#project-overview)  
- [Motivation](#motivation)  
- [Data Description](#data-description)  
- [Methodology](#methodology)  
- [Model Performance](#model-performance)  
- [Business Value](#business-value)  
- [Installation & Usage](#installation--usage)  
- [Future Work](#future-work)  
- [Author](#author)

---

## 🔍 Project Overview

This capstone project aims to build a predictive model that estimates how many goals an NHL player is expected to score in the upcoming season. The primary focus is on identifying patterns that can help stakeholders—teams, agents, and media—make informed decisions around player valuation.

---

## 💡 Motivation

- **Goals scored** remain one of the most visible and valued metrics for NHL forwards.
- This model provides a **data-driven tool** to compare player performance projections against salary expectations.
- It can help **spot undervalued or emerging talent**, and structure **endorsement deals** based on likely scoring output.

---

## 📊 Data Description

- **Target variable:** `goal`  
- **Type:** Binary classification (Goal or No Goal)
- **Imbalance ratio:** ~9.85 (far fewer goals than non-goals)
- **Handling Imbalance:**  
  - SMOTE (oversampling)  
  - Undersampling  
  - XGBoost’s `scale_pos_weight`  

*(Add dataset source, size, and preprocessing steps here if applicable)*

---

## 🧠 Methodology

- **Model Used:** `XGBoost Classifier`
- **Cross-validation:** 5-fold `RandomizedSearchCV`
- **Hyperparameters Tuned:**  
  `'n_estimators'`, `'learning_rate'`, `'max_depth'`, `'min_child_weight'`, `'gamma'`, `'lambda'`, `'alpha'`, `'scale_pos_weight'`
- **Evaluation Metric:** Mean F1 Score

---

## 📈 Model Performance

| Metric          | Value |
|-----------------|--------|
| Accuracy        | 0.74   |
| Precision       | 0.60   |
| Recall          | 0.77   |
| F1 Score        | 0.60   |
| ROC AUC Score   | 0.86   |

> ⚠️ Note: Due to class imbalance, recall and AUC were prioritized to ensure the model captures true goals effectively.

---

## 💼 Business Value

- **Recall of 0.77** means the model correctly identified ~78% of actual goals, making it well-suited for:
  - **Player Efficiency Analysis**
  - **Simulating Scoring Opportunities**
  - **Comparative Salary Negotiations**
  - **Endorsement Deal Planning**
  - **Scouting Breakout Candidates**

---

## 🚀 Future Work

- Improve class balance with ensemble methods or cost-sensitive learning  
- Incorporate additional advanced stats (e.g. xG, shot quality, time-on-ice per shift)  
- Extend to multi-season or player progression modeling  
- Deploy via a Flask web app or Streamlit dashboard  

---

## 👤 Author

**Travis Bates** 
Springboard Data Science Graduate  
LinkedIn:https://www.linkedin.com/in/travis-bates  
Email: bates.travis@outlook.com
