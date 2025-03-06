
# The Diabetes Dataset

This dataset contains 9,538 medical records related to diabetes diagnosis and risk factors. It includes various health parameters, lifestyle habits, and genetic predispositions that contribute to diabetes risk. 

### Key Features
- **Age**: The age of the individual (18-90 years).
- **Pregnancies**: Number of times the patient has been pregnant.
- **BMI** (Body Mass Index): A measure of body fat based on height and weight (kg/m²).
- **Glucose**: Blood glucose concentration (mg/dL), a key diabetes indicator.
- **BloodPressure**: Systolic blood pressure (mmHg), higher levels may indicate hypertension.
- **HbA1c**: Hemoglobin A1c level (%), representing average blood sugar over months.
- **LDL** (Low-Density Lipoprotein): "Bad" cholesterol level (mg/dL).
- **HDL** (High-Density Lipoprotein): "Good" cholesterol level (mg/dL).
- **Triglycerides**: Fat levels in the blood (mg/dL), high values increase diabetes risk.
- **WaistCircumference**: Waist measurement (cm), an indicator of central obesity.
- **HipCircumference**: Hip measurement (cm), used to calculate WHR.
- **WHR (Waist-to-Hip Ratio)**: Waist circumference divided by hip circumference.
- **FamilyHistory**: Indicates if the individual has a family history of diabetes (1 = Yes, 0 = No).
- **DietType**: Dietary habits (0 = Unbalanced, 1 = Balanced, 2 = Vegan/Vegetarian).
- **Hypertension**: Presence of high blood pressure (1 = Yes, 0 = No).
- **MedicationUse**: Indicates if the individual is taking medication (1 = Yes, 0 = No).
- **Outcome**: Diabetes diagnosis result (1 = Diabetes, 0 = No Diabetes).

## Summary

- **Total Features**: 17 numerical variables (a combination of numeric and categorical variables), 9538 rows
- **Target Variable**: Outcome

## The question to answer
What influences mostly the outcome of having Diabetes?
In our analysis we are aiming to analyse the relationship between different health markers and whether they contribute to Diabetes or not. The target variable for the categorical values is named `Outcome` and marks whether someone has Diabetes (1) or not (0).
The target variable for the numerical values is "Hb_a1C"

# How to follow along

- use analysis.ipynb to trace back the technical methods used to gather and analyse data
- check the Slides (hyperlink: XXXX) here for the business presentation