# CustomerChurnAnalysis_EDA
Performed EDA on a Customer Churn dataset, using Pandas, NumPy, Matplotlib, and Seaborn, I conducted statistical analysis and created visualizations to isolate the exact contract, billing, and service factors driving client flight, providing data-backed retention strategies.
# Telecom Customer Churn - Exploratory Data Analysis (EDA)
## Project Overview
This repository contains a comprehensive **Exploratory Data Analysis (EDA)** project focused on identifying the key drivers behind customer attrition (churn) for a telecommunications company[cite: 1]. The primary goal of this analysis is to uncover meaningful, data-driven patterns that separate retained customers from those who leave, providing actionable recommendations to maximize account longevity and reduce portfolio losses[cite: 1].

### Portfolio Baseline
* **Total Customer Profiles Analyzed:** 7,043 unique accounts[cite: 1]
* **Retained Customers (No Churn):** 5,174 (73.46%)[cite: 1]
* **Lost Customers (Churned):** 1,869 (26.54%)[cite: 1]

---

## Dataset Scope & Attributes
The analysis evaluates **21 operational, demographic, and financial attributes**[cite: 1]:
* **Demographics:** Gender, SeniorCitizen, Partner, Dependents[cite: 1].
* **Account Logistics:** Tenure, Contract, PaperlessBilling, PaymentMethod, MonthlyCharges, TotalCharges[cite: 1].
* **Services Subscribed:** PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies[cite: 1].
* **Target Variable:** Churn (Yes/No)[cite: 1].

---

## Preprocessing & Data Cleaning Workflow
To establish a statistically sound baseline, the raw data underwent a structured data engineering lifecycle within the notebook[cite: 1]:
1. **Structural Auditing:** Verified row-column boundaries (7,043 × 21) using Pandas[cite: 1].
2. **Null & Duplicate Assessment:** Confirmed **0 missing records** and **0 duplicate entries** across the rows[cite: 1]. Programmatically validated that there were **0 duplicate `customerID` instances**, ensuring data integrity[cite: 1].
3. **Data Type Correction:** Discovered that `TotalCharges` was loaded as a string object due to hidden blank spaces (`" "`)[cite: 1]. Replaced blanks with a baseline of `0` and forced a data type conversion to float (`float64`)[cite: 1].
4. **Feature Engineering:** Transformed the binary `SeniorCitizen` flag column (`0` / `1`) into human-readable categorical labels (`No` / `Yes`) using a custom mapping function[cite: 1].

---

## Key Analytical Insights

### 1. Financial & Lifespan Benchmarks
* **Revenue Profile:** The average monthly fee across accounts is **\$64.76**, with a median threshold of **\$70.35**[cite: 1]. The top 25% of premium plans generate between **\$89.85 and \$118.75 monthly**[cite: 1].
* **Lifecycle Value:** Retained long-term accounts accumulate up to **\$8,684.80** in total historical billing, averaging **\$2,279.73** per account over their lifespan[cite: 1].
* **Early Lifecycle Risk:** While the general lifespan average sits at **32.37 months**, the bottom 25% of consumers drop out sharply within their first **9 months**[cite: 1].

### 2. Demographic Vulnerabilities
* **Gender Neutrality:** Attrition is almost perfectly split between genders (**939 Females** vs. **930 Males**), showing **0 statistical correlation** between gender and customer flight[cite: 1].
* **Senior Attrition Density:** Senior Citizens comprise only **16.21%** of the general population but demonstrate a dramatically high density of churn, making them a volatile segment[cite: 1].

### 3. Contractual & Transactional Friction
* **Contract Architecture (The Leading Churn Predictor):** **Month-to-month contracts suffer from extreme risk**, making up **1,655 total churn cases—a massive 88.55% of all churned customers** in the portfolio[cite: 1]. Conversely, One-year and Two-year contracts remain completely stable[cite: 1].
* **Payment Friction:** Customers paying via manual **Electronic Check** represent **1,071 instances**, accounting for **57.30% of total portfolio losses**[cite: 1]. Automated payment mechanisms (Automatic Credit Card / Bank Transfer) show maximum account retention[cite: 1].

### 4. Product Portfolio Dependencies
* **Core Utilities:** Basic utilities like `PhoneService` and `MultipleLines` have a completely neutral effect on account churn[cite: 1].
* **Value-Added Services (VAS) as Core Stabilizers:** Subscribers lacking safety or utility add-ons—specifically **Online Security, Tech Support, Online Backup, and Device Protection**—churn at alarming rates[cite: 1]. Accounts with active safety subscriptions exhibit excellent structural longevity[cite: 1].
* **Internet Tech Type:** Customers utilizing **Fiber Optic** configurations experience drastically higher attrition rates compared to standard DSL users[cite: 1].

---

## Strategic Action Plan (Recommendations)

Based on the trends uncovered in this project, the following operational adjustments are recommended:

* **Month-to-Month Migration Campaigns:** Target Month-to-month accounts reaching their 6th or 9th monthly bill (the critical early drop-off window) with an automated incentive to transition onto a 1-year contract[cite: 1].
* **Transition Electronic Check Users:** Phase out manual transaction friction by applying a minor administrative handling fee to paper/manual options, while offering a one-time billing credit to clients who activate an automatic credit card or bank transfer channel[cite: 1].
* **Incentivize Safety Bundles:** Stop selling `Online Security` and `Tech Support` as separate a la carte features[cite: 1]. Bundle them natively into higher-risk internet lines (especially Fiber Optic) to build early environment integration[cite: 1].

---

## Repository Structure
```text
├── CustomerChurn_EDA.ipynb   # Main Jupyter Notebook containing the data cleaning & EDA[cite: 1]
├── CustomerChurn.csv         # Raw dataset containing the customer portfolio data[cite: 1]
└── CustomerChurnAnalysis.pdf # Project documentation and summary report
