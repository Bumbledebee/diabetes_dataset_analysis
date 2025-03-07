
# The Diabetes Dataset Analysis

## Scope of the project
The scope of this project is to wrap up all the learnings from the first three weeks of the Ironhack Machine Learning bootcamp on a suitable dataset which are as follows: Python, Pandas, EDA, Uni-, Bivariate Analyis.
The dataset could have been any other and the focus will on proceedings and methodology.
The goal is to understand the relationship between the values and to understand which values contribute the most to the target value.
In this case it would be "What health factors matter most for Diabetes?"

## The Diabetes Dataset

This dataset is from [Kaggle](=https://www.kaggle.com/datasets/asinow/diabetes-dataset) contains 9538 medical records related to diabetes diagnosis and risk factors. It includes various health parameters, lifestyle habits, and genetic predispositions that contribute to diabetes risk. 34% (3282) of the patients have diabetis and 66% (6256) do not have diabetis.
Below are the data collected per patient:

- **Age**: The age of the individual (18-90 years).
- **Pregnancies**: Number of times the patient has been pregnant.
- **BMI (Body Mass Index)**: A measure of body fat based on height and weight (kg/m²).
- **Glucose**: Blood glucose concentration (mg/dL), a key diabetes indicator.
- **BloodPressure**: Systolic blood pressure (mmHg), higher levels may indicate hypertension.
- **HbA1c Hemoglobin A1c**: Represents the average blood sugar over months.
- **LDL (Low-Density Lipoprotein)**: "Bad" cholesterol level (mg/dL).
- **HDL (High-Density Lipoprotein)**: "Good" cholesterol level (mg/dL).
- **Triglycerides**: Fat levels in the blood (mg/dL), high values increase diabetes risk.
- **WaistCircumference**: Waist measurement (cm), an indicator of central obesity.
- **HipCircumference**: Hip measurement (cm), used to calculate WHR (Waist-to-Hip Ratio).
- **WHR (Waist-to-Hip Ratio)**: Waist circumference divided by hip circumference.
- **FamilyHistory**: Indicates if the individual has a family history of diabetes (1 = Yes, 0 = No).
- **DietType**: Dietary habits (0 = Unbalanced, 1 = Balanced, 2 = Vegan/Vegetarian).
- **Hypertension**: Presence of high blood pressure (1 = Yes, 0 = No).
- **MedicationUse**: Indicates if the individual is taking medication (1 = Yes, 0 = No).
- **Outcome**: Diabetes diagnosis result (1 = Diabetes, 0 = No Diabetes).


# Steps of the analysis

## Data Cleaning

1. The file was checked for null values or empty strings. Nothing was found.
2. The column names got converted from CamelCase into snake_case
3. The numeric discrete columns of age and pregnancies were removed as I wanted to have two clean groups of numerical continous and categorical values.
4. The categorical columns are ['family_history', 'diet_type', 'hypertension', 'medication_use','outcome']. The target value for categorical is outcome. Outcome is 1,0 for Diabetes Yes or No.
5. The numerical columns are ['bmi', 'glucose', 'blood_pressure', 'ldl', 'hdl', 'triglycerides',
       'waist_circumference', 'hip_circumference', 'whr', 'hb_a1c']. The target value for numerical is hb_a1c and put as last column.
6. Furthermore, a dataframe for patients with Diabets and No Diabetis has been created.

Challenges encountered on the way:
- I had to adjust my default threshold of 20 when inserting numerical discrete values into the categorical group as the hb_a1c values for the No Diabetis patient group has only 19 unique numerical continous values which created a group imbalance in the beginning. I changed the order of doing this and would check the .nunique() earlier next time.

## Data Analysis 

Open this [link](https://docs.google.com/presentation/d/1S4drNo-kODkTmviWicpnEOEJBWnuWp6doipnTxOjpRc/edit#slide=id.g33ce38fb956_0_36) to follow along or check out the "Diabetes Dataset Analysis Presentation" pdf attached to this repository as well. The code can be found in analysis Jupyter Notebook and a copy of the plots is in the plots/ folder

### Categorical Value Analysis
1. Manual creation of a cross table for the Chi-Square P Value test for each categorical value with every other categorical value. The P value checks for statistical significance of the two values for not being independant.
Values being independant would be the null hypothesis that can be rejected with the p value being lower than the alpha which is often set at 0.05. The visualisation is done with the heatmap and we only need to focus on the last row.
2. Manual creation of a cross table for the Cramér's V test for each categorical value with every other categorical value. Cramer's V is a measure of association used to quantify the strength of the relationship between categorical variables.
Interpretation: Cramer's V ranges from 0 to 1, where 0 indicates no association, and 1 represents a perfect association between the variables. A higher value of Cramer's V indicates a stronger relationship between the categorical variables.
The visualisation is done with the heatmap and we only need to focus on the last row.
3. Frequency table for the values with the strongest association and statistical significance.

### Numerical Value Analysis
1. Automatic creation of a correlation heatmap with Spearman. The Spearman correlation coefficient indicates how monotonic (when one value grows the other one for sure does not decrease and the other way round) the relationship between the values is.
Again we only focus on the last row, which shows how our target goes against the other values.
2. Automatic creation of a correlation heatmap with Pearson. The Pearson correlation coefficient indicates how linear (when one value grows the other one grows as well and the other way round) the relationship between the values is.
Again we only focus on the last row, which shows how our target goes against the other values.
3. Plotting of the linear/monotonic relationships found in the previous steps
4. Plotting of the Side-by-Side Box Plot of the interesting values for each of the (categorical) target value.

## Conclusions
The conclusion that family history matters for having diabetes or not I could have guessed since there is a diabetis type which is genetically inherited. It is a flaw in the dataset that they do not have a column for diabetes type. Furthermore, that the relationship between glucose and hb_a1c is linear one could have guessed as both are a form of sugar in the blood, one more momentary and the other one more longterm. As the median blood sugar for the Diabets and No Diabetes group is pretty close I wonder if there could have been even more insights with including stages of pre-diabetes.
I now have in place a framework that enables me to quickly analyse any dataset thus judging if i worth continuing the analysis of the dataset or not. 

# Next steps
Next steps would be to create functions to quickly clean and analyse any new dataset. Moreover, I would include an automatic creation of simple frequency&proportion tables for the categorical values as well as distribution histograms and box plotting for all numerical values.