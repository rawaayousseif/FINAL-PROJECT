# FINAL-PROJECT
# Telecom Customer Churn Prediction

## Project Introduction

### Business Context

Customer churn is a major concern for subscription-based businesses, particularly in the telecommunications industry where market competition is high and acquisition costs are significant. The ability to accurately predict which customers are likely to leave enables proactive retention efforts, which are far more cost-effective than acquiring new customers.

The telecom provider in this case seeks to build a machine learning solution that identifies customers at high risk of churning so that the company can target them with personalized offers, service improvements, and contract incentives.

### Objective

The objective of this project was to build a robust predictive model that can classify customers as likely to churn or stay, using customer demographics, account details, and service usage information. Model performance is evaluated using the AUC-ROC metric, with a target threshold of ≥ 0.88 for highest business impact and full project credit.

## Data Overview

The project utilized customer data provided across multiple CSV files:

- `personal.csv`: demographic information (gender, senior citizen status, partner/dependents)
- `contract.csv`: contract type, start/end dates, monthly charges, payment method
- `internet.csv`: internet service type and subscriptions to value-added services
- `phone.csv`: use of multiple phone lines

The target variable `churn` was derived from the `EndDate` column.

## Work Plan

1. **Data Collection and Integration**
2. **Exploratory Data Analysis (EDA)**
3. **Data Preprocessing**
4. **Feature Engineering**
5. **Handling Class Imbalance**
6. **Model Development**
7. **Model Evaluation**
8. **Final Recommendation**

## Exploratory Data Analysis (EDA)

- Churn Rate: 26.5%
- Month-to-month contracts and fiber optic internet show highest churn.
- Customers using fewer services (no TechSupport, OnlineSecurity, etc.) churn more.
- Monthly charges are generally higher among churned customers.

## Modeling Results

| Model                       | AUC-ROC | Accuracy |
|----------------------------|---------|----------|
| Logistic Regression        | 0.8235  | 78.71%   |
| Decision Tree              | 0.6569  | 73.46%   |
| Random Forest (Balanced)   | 0.8357  | 76.37%   |
| LightGBM (Balanced)        | 0.8371  | 75.44%   |
| CatBoost (Tuned)           | 0.8465  | 80.55%   |
| 3-Model Stacking (Cat+RF+LGBM) | 0.8386 | 75.09% |
| SMOTE + Logistic Regression| 0.8225  | 72.89%   |

## Best Model

**CatBoostClassifier (tuned)** was selected as the final model for deployment:
- AUC-ROC: 0.8465
- Accuracy: 80.55%

## Recommendations

1. **Target high-risk churn customers** with offers and loyalty programs.
2. **Promote long-term contracts** to replace risky month-to-month plans.
3. **Upsell add-on services** like TechSupport and OnlineSecurity.
4. **Monitor payment methods**, especially electronic check users.
5. **Deploy the model and retrain quarterly** to maintain performance.

## Tools Used

- Python, Pandas, NumPy, Scikit-learn
- CatBoost, LightGBM, imbalanced-learn
- Jupyter Notebook, Matplotlib, Seaborn
- GitHub for version control

## Outcome

The project delivers a reliable, scalable machine learning model capable of assisting the company in reducing churn through targeted, data-driven interventions.
