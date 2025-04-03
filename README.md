# Retail Credit Risk Scorecard

A data-driven approach to evaluating customer credit risk using the "Give Me Some Credit" dataset

![screenshot-localhost_8888-2025 04 03-15_12_52](https://github.com/user-attachments/assets/940976ba-0926-4b9c-ae48-0e16a9ee1167)

### Overview

This project develops a transparent, points-based credit scorecard to assess customer default risk. Built using logistic regression and WOE (Weight of Evidence) binning, it transforms raw financial data into actionable risk scores (300–850 range). Designed for loan underwriting and portfolio risk management.

### Objectives

- Interpretable scoring system (points per risk factor)
-  Handles class imbalance (defaults are rare)
-  Regulatory-compliant (supports Basel III/IFRS 9)
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
- KS Statistic: 0.52 (strong separation)

### Conclusion

This scorecard provides a data-driven, regulatory-compliant approach to credit risk assessment. By focusing on behavioral patterns rather than static financial metrics, it offers a modern alternative to traditional scoring models.

### Source

![Home Credit Default Risk Dataset from Kaggle](https://www.kaggle.com/datasets/anggundwilestari/home-credit)
