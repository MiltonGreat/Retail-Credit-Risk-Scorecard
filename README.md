# Retail Credit Risk Scorecard

A data-driven approach to evaluating customer credit risk using the "Give Me Some Credit" dataset

### Overview

This project developed a high-performing credit risk scorecard using machine learning to evaluate customer default risk. 

### Objectives

- Interpretable scoring system (points per risk factor)
-  Handles class imbalance (defaults are rare)
- AUC 0.858 – Strong predictive power

### Dataset

Target: SeriousDlqin2yrs (1 = default within 2 years, 0 = no default)

Key Features Used

- Feature	Risk Impact
- RevolvingUtilizationOfUnsecuredLines	(Hig)h
- TotalPastDue (engineered)	(Very High)
- NumberOfTimes90DaysLate	(High)
- MonthlyIncome	(Medium)
- age	(Low)

### Methodology

1. Data Preprocessing
- Handled missing values (MonthlyIncome, NumberOfDependents)
- Engineered features (e.g., TotalPastDue = sum of all late payments)

2. Model Development
- Algorithm: Logistic Regression (class-weighted)
= Scorecard Conversion:
- Base Points: 600 (at 50:1 odds)
- PDO: 50 (points to double odds)
- Output: Transparent points allocation per feature bin.

3. Validation
- Train AUC: 0.8596 | Test AUC: 0.8580
- - Cross-Validation AUC | 0.8646 ± 0.0069

### Risk Segmentation

Risk Tier Cutoffs:

1. Very High Risk: < 550  (25.3% default rate)
2. High Risk: 550 - 590   (15.1%)
3. Medium Risk: 590 - 620 (6.8%) 
4. Low Risk: 620 - 650    (2.1%)
5. Very Low Risk: > 650   (0.5%)

### Source

![Give Me Some Credit Dataset from Kaggle](https://www.kaggle.com/c/GiveMeSomeCredit)
