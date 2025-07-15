# Package Pricing at Mission Hospital 
## Problem
Develop a predictive model that accurately forecasts the cost of medical treatments and procedures based on patient and clinical factors at time of admission.

### Objectives:
- Decide whether package pricing is appropriate vs. traditional itemized billing.
- Design a strategy to provide patients with accurate, transparent cost estimates upfront.
- Use package pricing as a competitive advantage to attract patients with clear and fair pricing.
- Predict total treatment cost given clinical factors on admission.

---

## Goal
This model aims to optimize pricing strategies for healthcare providers, improve financial transparency for patients, and overall improve efficiency of the healthcare system through data-driven decisions.

### What is package pricing?
**Package Pricing:** offers patients a bundled quote for an episode of care.

--- 

## Resources

- **Project Idea:** https://365datascience.com/career-advice/top-10-data-science-project-ideas/#2
- **Data Source:** https://github.com/rashidesai24/Package-Pricing-at-Mission-Hospital/blob/main/Package%20Pricing%20at%20Mission%20Hospital%20-%20Data%20Supplement.xlsx

---

## Data Preparation 

### Categorial Features
| Feature | Categories |
|---|---|
| **Age** | <10, 11-25, 26-50, >50 and above (as per domain expertise) |
| **Blood Pressure (BP)** | Low, Normal, High, Critical (from medical guidelines) |
| **BMI** | Underweight, Normal, Overweight, Obese |
|**Hemoglobin** | Normal/Abnormal (Female: 12-15.5, Male: 13-17.5) |
| **Urea** | Normal/Abnormal (Normal: 7-20 mg/dL) |
|**Creatinine Categories:** Age <3 & creatinine: 0.3-0.7 -> Normal, Age: 3-18 & creatinine: 0.5-1.0 -> Normal, Age >18 & Female & creatinine: 0.6 - 1.1 ->	Normal,
Age > 18 & Male & creatinine: 0.9 - 1.3 ->	Normal, Else: Abnormal |

---

### Feature Engineering & Cleaning
- **Removed Variables:**
    - **Stay at hospital ICU** and **Stay in Ward** were removed because they are reflective construct variables. Additionally, it is not possible to predict length of stay accurately at time of admission.

- **Target Variable Transformation:**
    - The **Total Cost To Hospital** was **log-transformed** to address right skewness in the distribution.

- **Handling Null Values:**
    - **BP Range:** Missing values imputed as 'Normal'
    - **Urea:** Misisng values imputed as 'Normal'

---

## Modeling Approach

### Models Built:

1. **Linear Regression (Baseline)**
   - RMSE (log scale): **0.4149**
   - R²: **0.2557**
   - Feature coefficients analyzed for interpretability.

2. **Lasso Regression (L1 Regularization)**
   - RMSE (log scale): **0.4159**
   - R²: **0.2522**
   - Performed feature shrinkage but did not significantly outperform Linear Regression.

3. **Random Forest Regressor**
   - RMSE (log scale): **0.4359**
   - R²: **0.1785**
   - Feature importance identified non-linear interactions but model performance was slightly worse.

---

## Residual Analysis

- **Residuals vs Predicted Plot**  
  Checked for patterns; slight right skew detected.

- **Histogram of Residuals**  
  Slight right-skewness observed; potential for further normalization or different loss functions.

---