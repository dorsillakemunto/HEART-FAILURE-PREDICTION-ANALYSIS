# Heart Failure Prediction Analysis

## 📌 Project Overview
This project explores the use of data analysis and machine learning techniques to investigate factors associated with the presence of heart disease. The project uses the Heart Failure Prediction Dataset from Kaggle. The dataset contains 918 observations, 11 predictor variables, and a binary target variable, HeartDisease.

## 🎯 Project Objective
The main objectives of this project are to: Understand the structure and quality of the dataset. Perform data preprocessing and cleaning. Apply feature engineering techniques. Conduct exploratory data analysis. Investigate relationships between clinical variables and heart disease. Perform statistical hypothesis testing. Analyze correlations and potential multicollinearity. Investigate outliers and feature distributions. Prepare the dataset for subsequent machine learning modeling. 

## 📊 Dataset & Repository Structure
The dataset contains 918 observations and 12 variables. To maintain a clean workflow, the project tracking files are organized as follows:
```text
├── data/
│ ├── raw/
│ ├── processed/
│ ├── notebooks/
│ │ └── heart_original.csv # The baseline, untouched dataset
│ │ └── heart_cleaned.csv # Dataset after initial anomaly/outlier fixes
│ └── models/
│ └── heart_ml_ready.csv # Encoded, scaled dataset ready for training
│ └── heart_disease_ml_ready.csv # Dataset after advanced EDA, Statistical Analysis & Feature Engineering
```
##Technologies 
-Python 
-Pandas 
-NumPy 
-Matplotlib 
-Seaborn 
-SciPy 
-Scikit-learn 
-Google Colab 
-GitHub 

### Main Dataset Variables:
* **Age**, **Sex**, **ChestPainType**, **RestingBP**, **Cholesterol**, **FastingBS**, **RestingECG**, **MaxHR**, **ExerciseAngina**, **Oldpeak**, **ST_Slope**, **HeartDisease**

### Target Variable:
The target variable is `HeartDisease`:
* `0` = No heart disease
* `1` = Heart disease
This makes the project a binary classification problem.

## 🧹 Data Preprocessing
The dataset was inspected and prepared using several preprocessing steps.

### Missing Values and Duplicates
The dataset was checked for missing values and duplicate records.
* **Result:** No missing values or duplicate records were found.

### Categorical Variables
The following categorical variables were identified: `Sex`, `ChestPainType`, `RestingECG`, `ExerciseAngina`, `ST_Slope`.
These variables were transformed using **One-Hot Encoding** because their categories do not have a natural numerical order.

### Binary Variable
`FastingBS` was retained as a binary numerical variable because it already represents two possible states. The target variable, `HeartDisease`, was kept separate and was not scaled.

### Numerical Variables
The following continuous variables were standardized using `StandardScaler` because they have different numerical ranges, which can affect sensitive machine-learning algorithms:
* `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`

## 🔎 Outlier and Anomaly Handling
Potential outliers and unusual observations were investigated using boxplots and the **Interquartile Range (IQR)** method:
Lower Bound = Q1 - 1.5 * IQR, 
Upper Bound = Q3 + 1.5 * IQR

During the investigation, specific issues were identified and handled:
* **Cholesterol:** Extreme values were handled using **median replacement** to ensure a robust measure of central tendency.
* **Oldpeak & RestingBP:** Anomalous values were investigated and corrected. Extreme clinical observations were not removed automatically; adjustments were made only where data points were true anomalies rather than valid, rare clinical measurements.

## 📈 Feature Relevance
Feature relevance was investigated using three distinct approaches to provide a broader understanding:
1. **Correlation Analysis:** To examine relationships between numerical variables and identify potentially redundant features.
2. **Random Forest Feature Importance:** To identify variables that contribute strongly to predictions.
3. **Mutual Information:** To identify features that contain useful information about the target.

## 🔄 Preprocessing Pipeline
A preprocessing pipeline was used to ensure that transformations were fitted using the training data only and then applied to the test data. This approach helped prevent data leakage.

```text
Raw Dataset ↓ 
Data Inspection ↓ 
Data-Type Validation ↓ 
Missing Value & Duplicate Check ↓ 
Outlier and Anomaly Detection ↓ 
Outlier/Anomaly Handling ↓ 
Train/Test Split ↓ 
One-Hot Encoding ↓ 
Numerical Scaling ↓ 
Feature Relevance Analysis ↓ 
Machine-Learning-Ready Dataset
```

## ✅ Machine-Learning Readiness
After preprocessing, the dataset has:
* Validated data types without missing values or duplicate records
* Corrected anomalies in `Oldpeak` and `RestingBP`
* Handled extreme `Cholesterol` values via median replacement
* Encoded categorical variables and scaled continuous variables
* A clearly separated target variable
* A leakage-protected preprocessing pipeline split

## 📌 Key Findings

| Data Issue | Method Used |
| :--- | :--- |
| Missing values / Duplicate records | Checked – none found |
| Categorical variables | One-Hot Encoding |
| Binary variable | Retained as binary |
| Continuous variables | StandardScaler |
| Cholesterol outliers | Median replacement |
| Oldpeak / RestingBP anomalies | Investigated and corrected |
| Potential outliers | IQR and boxplots |
| Feature relationships | Correlation analysis |
| Feature importance | Random Forest |
| Feature information | Mutual Information |
| Data leakage prevention | Training-data-only preprocessing pipeline |

##Statistical Analysis 

Statistical testing was incorporated to move beyond visual exploration and evaluate whether observed relationships were statistically significant.
The analysis includes: Independent-samples t-tests for selected numerical variables. Chi-square tests of independence for categorical variables. Effect-size analysis to assess the strength of categorical associations. Correlation analysis for numerical variables. 
A significance level of α = 0.05 was used for hypothesis testing.

## 🚀 Future Work
The prepared dataset (`data/models/heart_disease_ml_ready.csv`) is ready for subsequent machine-learning tasks:
* Training classification models and comparing algorithms
* Feature selection
* Cross-validation and model evaluation / interpretation
* Assessing model fairness and reliability

## ⚠️ Disclaimer
This project is intended for research and educational purposes only. The dataset and any machine-learning model developed from it should not be interpreted as a clinical diagnostic system. Real-world clinical use would require additional validation on representative patient populations, medical oversight, and evaluation of the model's safety, fairness, and reliability.

## 📝 Conclusion
The Heart Failure Prediction Dataset has been thoroughly inspected, cleaned, transformed, and organized into structured directory stages (`raw`, `processed`, `models`). The resulting datasets provide a reliable, leakage-free foundation for future binary classification modeling tasks.
