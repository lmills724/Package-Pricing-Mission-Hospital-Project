# Package Pricing at Mission Hospital 
## Problem
Develop a predictive model that accurately forecasts the cost of medical treatments and procedures.
- Decide whether to use package pricing or traditional pricing
- Design a strategy as an accurate approach to predict package price at time of admission
- Determine how to use package pricing as competitive strategy
- Estimate the price of treatment given clinical factors at time of admission

## Goal
This model aims to optimize pricing strategies for healthcare providers, provide financial transparency for patients, and overall improve efficiency of the healthcare system through data-driven decisions.

**Package Pricing:** Patients are provided a tailored quote on treatment cost at the time of admission for a group of related services, which is based on the expected costs for a clinically defined episode of care.

## Resources

- **Project Idea:** https://365datascience.com/career-advice/top-10-data-science-project-ideas/#2
- **Data Source:** https://github.com/rashidesai24/Package-Pricing-at-Mission-Hospital/blob/main/Package%20Pricing%20at%20Mission%20Hospital%20-%20Data%20Supplement.xlsx

## Data Preparation 

- **Age Categories:** <10, 11-25, 26-50, >50 and above (as per domain expertise) 
- **BP Ranges:** Low, Normal, High, Critical (as per the medical charts)
- **BMI:** Underweight, Normal, Overweight, Obese (as per the medical charts)
- **Hemoglobin:** normal - Female 12 to 15.5, Men 13 to 17.5, any value outside these limits will be abnormal
- **Urea:** normal - 7 to 20 mg/dl any value outside these limits will be "abrnormal"
- **Creatinine Categories:** Age <3 & creatinine: 0.3-0.7 -> Normal, Age: 3-18 & creatinine: 0.5-1.0 -> Normal, Age >18 & Female & creatinine: 0.6 - 1.1 ->	Normal,
Age > 18 & Male & creatinine: 0.9 - 1.3 ->	Normal, Else: Abnormal