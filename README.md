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
**Package Pricing** offers patients a bundled quote for an episode of care.

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
|**Creatinine Categories:** | Age <3 & creatinine: 0.3-0.7 -> Normal, Age: 3-18 & creatinine: 0.5-1.0 -> Normal, Age >18 & Female & creatinine: 0.6 - 1.1 ->	Normal, Age > 18 & Male & creatinine: 0.9 - 1.3 ->	Normal, Else: Abnormal |


![Categorical Variable Distribution Plots](./images/Categorical%20Variable%20Distributions.png)
---

### Feature Engineering & Cleaning
- **Removed Variables:**
    - **Stay at hospital ICU** and **Stay in Ward** were removed because they are reflective construct variables. Additionally, it is not possible to predict length of stay accurately at time of admission.

- **Target Variable Transformation:**
    - The **Total Cost To Hospital** was **log-transformed** to address right skewness in the distribution.
![Target Variable Distribution Before/After Log Transformation](./images/Total%20Cost%20Log%20Plots.png)

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

### Model Performance and Residual Analysis Plots
![Actual vs Predicted and Residual Plots - LR Model](./images/avp%20residuals%20LR.png)
![Actual vs Predicted and Residual Plots - Lasso Model](./images/avp%20residuals%20LASSO.png)
![Actual vs Predicted and Residual Plots - RF Model](./images/avp%20residuals%20RF.png)
---

### Learning Curve Analysis
![Learning Curve Plots of LR, Lasso, and RF Models](./images/Learning%20Curve%20Comparison.png)

---

## Conclusion
Based on this analysis and modeling of treatment cost data at Mission Hospital, there are important considerations regarding implementing package pricing.

### **Should Mission Hospital Implement Package Pricing?**
**Pros:**
- **Improved Cost Transparency:** Provides patients with upfront cost estimates, improving trust and satisfaction.
- **Operational Efficiency:** Simplifies billing by bundling related services.
- **Data-Driven Approach:** Models can inform pricing decisions using clinical and demographic data at time of admission.

**Cons:**
- **Prediction Limitations:** Current models explain only part of cost variability, risking inaccurate estimates.
- **Not Universally Applicable:** Package pricing may not be sucessful for rare or highly variable treatments.

### **Recommendation**
Mission Hospital should consider a **targeted rollout of package pricing** for standardized, lower-variability procedures. Over time, continued data collection and model refinement will be crucial for minimizing risk and improving cost predictions.