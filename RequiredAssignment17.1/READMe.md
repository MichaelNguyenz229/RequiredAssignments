# Bank Marketing Campaign Optimization: Classifier Comparison for Targeted Marketing

## Project Overview

**Goal:** To compare the performance of multiple machine learning classifiers and identify the most effective model for predicting term deposit subscriptions in a Portuguese bank's telephone marketing campaigns.

**Client:** A Portuguese banking institution seeking to improve marketing campaign efficiency and reduce wasted call center resources.

**Framework:** This project evaluates four classification algorithms (K-Nearest Neighbors, Logistic Regression, Decision Trees, and Support Vector Machines) using standard machine learning best practices including cross-validation, hyperparameter tuning, and appropriate metrics for imbalanced datasets.

## Key Findings (Executive Summary)

Based on an analysis of over 41,000 customer records and a tuned Decision Tree model (F1-Score: 0.255, Recall: 53.9%), the following actionable insights were identified for the marketing team:

1. **Students Are Golden:**
   - Students subscribe at **31.4%** - nearly **3x the overall average** of 11.3%.
   - Retirees follow at **25.2%** (2.2x average).
   - *Action:* Prioritize outreach to students and retirees; create targeted messaging emphasizing long-term planning (students) and security (retirees).

2. **Avoid Blue-Collar Segments:**
   - Blue-collar workers subscribe at only **6.9%** - 39% below average.
   - Service industry workers are similarly low at **8.1%**.
   - *Action:* Deprioritize these segments or use lower-cost channels (email/SMS instead of phone calls).

3. **The Class Imbalance Problem:**
   - With 88.7% of customers saying "no," standard accuracy metrics are misleading.
   - Initial models achieved 88.7% accuracy by simply predicting "no" for everyone - completely useless.
   - *Action:* Use F1-score, Recall, and Precision as success metrics, not accuracy.

4. **Targeted Calling Strategy:**
   - The Decision Tree model enables **64% reduction in calls** (from 10,000 to 3,600).
   - Captures **54% of potential subscribers** while reducing wasted effort by 67%.
   - Success rate improves from 11.3% to 17%.
   - *Trade-off:* Miss 46% of potential subscribers to achieve cost savings.

## Methodology

### 1. Business Understanding
The objective was to build a predictive model that identifies customers most likely to subscribe to term deposits, enabling the bank to focus marketing resources on high-probability prospects rather than mass-calling all customers.

### 2. Data Understanding & Preparation
- **Source:** UCI Machine Learning Repository - Bank Marketing Dataset.
- **Records:** 41,188 customers with 20 features (demographics, campaign history, economic indicators).
- **Cleaning:** Identified 'unknown' values in categorical features; handled pdays placeholder (999 = not previously contacted).
- **Feature Engineering:** One-hot encoded categorical variables; applied class balancing to address 88.7%/11.3% imbalance.

### 3. Modeling
Four classification algorithms were evaluated:
- **Baseline Models:** Default settings with class balancing where supported.
- **Tuned Models:** GridSearchCV with 5-fold cross-validation, optimizing for F1-score.

### 4. Evaluation
- **Performance Metric:** F1-Score (balances Precision and Recall for imbalanced data).
- **Best Model:** Decision Tree achieved F1-Score of 0.255 with 53.9% recall and 16.7% precision.
- **Comparison:** Logistic Regression was close second (62.2% recall but slightly lower F1); KNN performed poorly (9.1% recall).

## Model Comparison Results

| Model | F1-Score | Recall | Precision | ROC-AUC | Best Hyperparameters |
|-------|----------|--------|-----------|---------|----------------------|
| **Decision Tree** | **0.255** | 53.9% | 16.7% | 0.640 | max_depth=10, min_samples_split=20 |
| Logistic Regression | 0.252 | 62.2% | 15.8% | 0.650 | C=10, penalty='l2' |
| K-Nearest Neighbors | 0.129 | 9.1% | 22.6% | 0.571 | n_neighbors=3, weights='distance' |

**Note:** SVM excluded due to computational cost with minimal expected performance gain.

## Recommendations

To maximize campaign ROI, the marketing team should:

1. **Immediate Actions:**
   - Segment customer database by job type and age.
   - Deploy the Decision Tree model to score all customers with subscription probability.
   - In next campaign: Call top 2,000-3,000 highest-probability customers first.

2. **Pilot Testing:**
   - A/B test: 50% model-driven targeting vs. 50% traditional mass calling.
   - Measure: conversion rate, cost per acquisition, customer satisfaction.

3. **Long-term Strategy:**
   - Develop job-specific messaging (student-focused: flexibility; retiree-focused: guaranteed returns).
   - Collect additional features (income, account balance) to improve model.
   - Implement real-time scoring API for call center agents.

4. **What to Avoid:**
   - Don't rely on accuracy as a success metric with imbalanced data.
   - Don't mass-call low-probability segments (blue-collar, service workers).
   - Don't assume housing/personal loan status matters (data shows minimal impact).

## Repository Structure

- `data/`: Contains the bank marketing dataset (bank-additional-full.csv).
- `prompt_III.ipynb`: The Jupyter Notebook containing the full analysis and code. [View Notebook Here](assignment17_1_starter/prompt_III.ipynb)
- `README.md`: This file.

---

*Author: [Michael Nguyen]*  
*Date: January 11, 2026*  
*UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence*
