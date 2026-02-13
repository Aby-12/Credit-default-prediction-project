# Credit-default-prediction-project
Phase 3 project- credit-default prediction  modelling

# Predicting credit default risk to reduce financial losses in banks and financial institutions

## Overview

This project develops classification models to predict whether a credit card client will default on their payment in the following month. By identifying high-risk borrowers in advance, financial institutions can reduce expected losses, improve credit risk management, and take proactive intervention measures.

The final selected model prioritizes identifying defaulters, aligning with the business objective of minimizing financial exposure.

---

## Business and data understanding

### Business problem

Financial institutions incur significant losses when customers default on credit obligations. The objective of this project is to predict next-month default risk in order to:

- Reduce financial losses
- Improve credit risk assessment
- Enable early intervention strategies

### Stakeholders

**Primary stakeholders**
- Credit risk and risk analytics teams

**Secondary stakeholders**
- Product managers managing pricing and credit limits
- Collections teams prioritizing outreach
- Senior management monitoring portfolio risk

### Dataset

The dataset used is the UCI Credit Card Default dataset, containing 30,000 credit card clients. It includes:

- Demographic information
- Credit limits
- Repayment history over six months
- Billing amounts
- Payment amounts
- Default status in the following month

The target variable is:
- `default.payment.next.month`  
  - 1 = Default  
  - 0 = No Default  

This is a binary classification problem.

---

## Modeling

Several classification models were evaluated:

1. Logistic Regression (Baseline)
2. Logistic Regression with class weighting (to address class imbalance)
3. Decision Tree
4. Decision Tree with class weighting

Because the dataset is imbalanced, recall for the default class was prioritized. Class weighting was applied to penalize misclassification of defaulters more heavily.

The balanced logistic regression model achieved the strongest performance in identifying defaulters.

---

## Evaluation

The final selected model (Balanced Logistic Regression) achieved:

- Recall (Defaulters): 63%
- Precision (Defaulters): 36%
- Accuracy: 76%
- AUC: 0.70%

The model reduces missed defaulters from 1,009 in the baseline model to 504, cutting false negatives nearly in half.

This improvement significantly enhances the institution’s ability to identify high-risk borrowers.

---
## Limitations
- Higher recall reduces precision, so some low-risk borrowers may be flagged.
- The model relies on historical data and requires ongoing monitoring.

## Conclusion

The balanced logistic regression model provides the best trade-off between risk detection and overall performance. Recent repayment behavior was identified as the strongest predictor of default risk.

The model can be deployed as a screening tool

## Recommendations

- Monitor customers with recent payment delays.
- Implement early intervention for at-risk borrowers.
- Review and adjust credit limits based on risk.
- Use the model to flag high-risk accounts for further review.
