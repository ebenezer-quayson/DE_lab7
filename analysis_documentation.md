# Heart Disease Prediction - Data Analysis

This document provides a summary of the analysis performed on a dataset containing various features related to heart disease prediction. The dataset includes both categorical and numerical data, which are used to predict the likelihood of heart disease.

## Key Features

1. **`age`**: Age in years
2. **`sex`**: Gender (1 = male, 0 = female)
3. **`cp`**: Chest pain type
    - Value 1: Typical angina
    - Value 2: Atypical angina
    - Value 3: Non-anginal pain
    - Value 4: Asymptomatic
4. **`trestbps`**: Resting blood pressure (in mm Hg on admission to the hospital)
5. **`chol`**: Serum cholesterol in mg/dl
6. **`fbs`**: Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)
7. **`restecg`**: Resting electrocardiographic results
    - Value 0: Normal
    - Value 1: ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
    - Value 2: Probable or definite left ventricular hypertrophy
8. **`thalach`**: Maximum heart rate achieved in an exercise test
9. **`exang`**: Exercise induced angina (1 = yes; 0 = no)
10. **`oldpeak`**: ST depression induced by exercise relative to rest
11. **`slope`**: The slope of the peak exercise ST segment
    - Value 1: Upsloping
    - Value 2: Flat
    - Value 3: Downsloping
12. **`ca`**: Number of major vessels colored by fluoroscopy (0-3)
13. **`thal`**: Thalassemia test results
    - Value 3: Normal
    - Value 6: Fixed defect
    - Value 7: Reversible defect
14. **`heart_disease`**: Diagnosis of heart disease (angiographic disease status)
    - Value 0: No heart disease (less than 50% narrowing of coronary arteries)
    - Value 1-4: Presence of heart disease (greater than 50% narrowing)

## Summary of Measures of Central Tendency and Dispersion

Here is a summary of the central tendency (mean, median) and dispersion (standard deviation, min, max) for the features in the dataset:

| Feature      | Count | Mean      | Std Dev   | Min  | 25%  | Median | 75%  | Max  |
|--------------|-------|-----------|-----------|------|------|--------|------|------|
| `age`        | 303   | 54.44     | 9.04      | 29   | 48   | 56     | 61   | 77   |
| `sex`        | 303   | 0.68      | 0.47      | 0    | 0    | 1      | 1    | 1    |
| `cp`         | 303   | 3.16      | 0.96      | 1    | 3    | 3      | 4    | 4    |
| `trestbps`   | 303   | 131.69    | 17.60     | 94   | 120  | 130    | 140  | 200  |
| `chol`       | 303   | 246.69    | 51.78     | 126  | 211  | 241    | 275  | 564  |
| `fbs`        | 303   | 0.15      | 0.36      | 0    | 0    | 0      | 0    | 1    |
| `restecg`    | 303   | 0.99      | 0.99      | 0    | 0    | 1      | 2    | 2    |
| `thalach`    | 303   | 149.61    | 22.88     | 71   | 133  | 153    | 166  | 202  |
| `exang`      | 303   | 0.33      | 0.47      | 0    | 0    | 0      | 1    | 1    |
| `oldpeak`    | 303   | 1.04      | 0.62      | 0    | 1    | 0.80   | 1.60 | 6.20 |
| `slope`      | 299   | 1.60      | 0.94      | 1    | 1    | 2      | 2    | 3    |
| `ca`         | 301   | 0.67      | 0.94      | 0    | 0    | 0      | 1    | 3    |
| `thal`       | 303   | 4.73      | 1.94      | 3    | 3    | 3      | 7    | 7    |
| `heart_disease` | 303 | 0.94     | 1.23      | 0    | 0    | 0      | 2    | 4    |

### **Key Observations**

- **`age`**: The average age is 54.44 years, with a range from 29 to 77 years. The distribution is fairly spread out with some older individuals.
- **`sex`**: The dataset has a higher number of males (sex = 1), with the majority of entries being male.
- **`cp` (Chest Pain Type)**: The majority of individuals have either typical angina (value 1) or asymptomatic pain (value 4), with a smaller proportion reporting atypical angina (value 2).
- **`trestbps` (Resting Blood Pressure)**: The mean is 131.69 mm Hg, which is on the higher end, with values ranging from 94 to 200 mm Hg.
- **`chol` (Serum Cholesterol)**: The average serum cholesterol level is 246.69 mg/dl, with a wide range from 126 mg/dl to 564 mg/dl, indicating variability in cholesterol levels.
- **`fbs` (Fasting Blood Sugar)**: Only 15% of the dataset has fasting blood sugar greater than 120 mg/dl (value 1).
- **`restecg` (Resting Electrocardiographic Results)**: Most individuals have normal results (value 0), but a considerable number also show ST-T wave abnormality (value 1).
- **`thalach` (Maximum Heart Rate Achieved)**: The mean is 149.61 bpm, with a range from 71 to 202 bpm, showing variation in heart rate during exercise.
- **`exang` (Exercise Induced Angina)**: About 33% of individuals experienced exercise-induced angina (value 1).
- **`oldpeak`**: The average ST depression caused by exercise relative to rest is 1.04, with a maximum of 6.2.
- **`slope` (Slope of Peak Exercise ST Segment)**: The most common slope type is flat (value 2), followed by upsloping (value 1).
- **`ca` (Number of Major Vessels)**: The majority of people have 0 or 1 major vessel affected, with a few cases showing 3 vessels affected.
- **`thal` (Thalassemia Test Results)**: Most individuals have normal results (value 3), while others show fixed or reversible defects (values 6 and 7).
- **`heart_disease`**: The majority of individuals have a diagnosis of heart disease (values 1, 2, 3, 4), with a smaller number showing no disease (value 0).

## Correlation Analysis

The correlation analysis was performed to understand the relationships between the various features in the dataset and how they relate to heart disease.

### **Key Observations for Predictors of Heart Disease**

1. **`cp` (Chest Pain Type)**: Moderate positive correlation (0.407) with heart disease. Typical and atypical chest pain are significantly associated with heart disease.
2. **`oldpeak` (ST depression induced by exercise)**: Strong positive correlation (0.504) with heart disease. A higher degree of ST depression indicates a higher risk of heart disease.
3. **`ca` (Number of major vessels affected)**: Strong positive correlation (0.521) with heart disease. More affected vessels suggest more severe heart disease.
4. **`thal` (Thalassemia Test Results)**: Strong positive correlation (0.501) with heart disease, indicating that abnormalities in the test are linked to heart disease.
5. **`thalach` (Maximum heart rate achieved)**: Negative correlation (-0.415) with heart disease. A lower maximum heart rate achieved during exercise is linked to a higher risk of heart disease.
6. **`exang` (Exercise Induced Angina)**: Moderate positive correlation (0.397) with heart disease. People who experience chest pain during exercise are more likely to have heart disease.
7. **`age`**: Moderate positive correlation (0.223) with heart disease. Older individuals tend to have a higher likelihood of heart disease.
8. **`sex`**: Moderate positive correlation (0.224) with heart disease. Males are at a higher risk compared to females, but the correlation is moderate.

### **Weak or No Significant Correlations**
- **`chol` (Serum cholesterol)**: Weak correlation (0.071) with heart disease.
- **`fbs` (Fasting blood sugar)**: Very weak correlation (0.059) with heart disease.
- **`trestbps` (Resting blood pressure)**: Weak correlation (0.158) with heart disease.
- **`restecg` (Resting electrocardiographic results)**: Weak correlation (0.184) with heart disease.
- **`slope` (Slope of the peak exercise ST segment)**: Moderate positive correlation (0.378) with heart disease.

## Conclusion

- **Strongest Predictors**: The most significant predictors of heart disease are **`oldpeak`**, **`ca`**, **`thal`**, and **`cp`**.
- **Age and Gender**: Age and gender have moderate correlations with heart disease, with males and older individuals being at higher risk.
- **Other Features**: While features like cholesterol, fasting blood sugar, and blood pressure have weak correlations with heart disease, they still contribute to overall health risk assessment.

This analysis reveals that the presence of **chest pain**, **ST depression during exercise**, **number of affected vessels**, and **thalassemia abnormalities** are strong indicators of heart disease, while age and gender also play a moderate role in predicting the condition.
