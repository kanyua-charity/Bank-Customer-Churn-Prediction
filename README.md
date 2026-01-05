# BANK CUSTOMER-CHURN PREDICTION



**Charity Nduku Kanyua - DSF-FT14**
**Instructor - Diana Mongina**

---

## Project Overview

This project aims to predict whether a bank customer will stop doing business with ABC Bank based on various criteria. This analysis will help the bank to identify customers at risk of churning and deploy retention campaigns, but at the same time, keep things cost-effective.



## Business Problem

ABC Bank has realised that some of its customers are likely to stop doing business with them. An analysis of various factors is conducted to determine which customers are likely to churn, and how they can be retained.

### Objectives

1. To identify the customers that are at high risk of churning.

2. To minimise the number of missed churners.

3. To come up with cost-effective interventions for customer churn.

---

## Dataset

### Data Source

The analysis integrates data from the ABC Multistate Bank database via Kaggle.

**Key Features**

General Information
This dataset is for ABC Multistate bank with following columns:


- customer_id: unused variable -> Account Number
- credit_score
- country -> Country of Residence
- gender
- age
- tenure -> Number of years a customer has held an      account in ABC Bank
- balance -> Account Balance
- products_number -> Number of products the customer has interacted with
- credit_card -> Indicates whether a customer has a credit card
- active_member -> Indicates whether a customer is active
- estimated_salary -> salary of Account holder
- churn: used as the target. 1 if the customer has left the bank during some period or 0 if he/she has not


## Exploratory Data Analysis

- Checked for missing values (none found). - Distribution of target variable shows **class imbalance**: 
    - Non‑churners: ~80% 
    - Churners: ~20% 
- Feature engineering: 
    - Created `credit_group` categories. 
    - Added `risk_indicator` feature for customers with   low credit score but high balance.

---

## Methodology

**Data Preprocessing**
- One‑Hot Encoding for categorical variables. 
- Standardization of numeric features. 
- Train‑test split(70/30).

**Models Implemented**
- Logistic Regression (baseline) 
- Logistic Regression with class weights
- Decision Tree Classifier(balanced class weights)
- Random Forest Classifier

## Results

**Baseline Logistic Regression:** 
- Precision: 0.62 
- Recall: 0.23 
- F1‑score: 0.34 

**Weighted Logistic Regression:** 
- Precision: 0.38 
- Recall: 0.70 
- F1‑score: 0.49 

**First Decision Tree** 
- Precision: 0.45
- Recall: 0.79 
- F1-score: 0.57
(high recall, lower precision)

**Decision Tree with Tuned Hyperparameters:** 
- Precision: 0.47
- Recall: 0.77
- F1-score: 0.58

**Random Forest Classifier**
- Precision: 0.50
- Recall: 0.77
- F1-score: 0.61
(High recall, improved precision)

---

## Key Insights
- **Tradeoff observed:** Models with high recall tend to have lower precision, and vice versa.

- **Decision Tree:** Captures churners well (high recall) but misclassifies many non‑churners.

- **Random Forest:** Provides more stable and balanced predictions.

- **Business implication:** False negatives (missed churners) are more costly than false positives, so recall is prioritized, but precision must remain acceptable to avoid unnecessary interventions.

---

## Recommendations

**1. Customer Retention Campaigns**
- Targeted offers: Provide loyalty rewards, discounts, or personalized packages to customers flagged as high churn risk.

- Proactive outreach: Assign  customer service representives to engage at‑risk customers before they leave.

- Feedback loops: Collect feedback from churn‑prone customers to understand dissatisfaction drivers (e.g., fees, service quality).

**2.Product and Service Improvements**
- Simplify product offerings: Customers with multiple products tend to stay longer; encourage bundling services.

- Improve digital experience: Enhance mobile banking apps and online platforms to increase engagement.

**3. Risk Management**
- Credit score monitoring: Customers with lower credit scores and high balances may be more volatile. Offer financial counseling or credit improvement programs.

- Early warning system: Use churn predictions to trigger alerts for account managers to intervene

---

## Technical Stack

### Programming Language
- **Python 3.8+**

### Core Libraries
- **pandas** — Data loading, cleaning, and manipulation
- **numpy** — Numerical computing
- **matplotlib** — Data visualization
- **seaborn** — Statistical data visualization
- **sklearn** — Preprocessing, model selection, models,    evaluation
- **imblearn** — SMOTE to handle imbalanced dataset


---

## Contributors

**Charity Nduku Kanyua**
- Project analysis conducted as part of Data Science coursework
- Full Time Hybrid program

---

## License

This project is available for educational and reference purposes.

---

## Contact

For questions or collaboration opportunities, please open an issue in the GitHub repository.

---

## Acknowledgments

- Data provided by Kaggle
- Analysis conducted under the guidance of Instructor Diana Mongina








