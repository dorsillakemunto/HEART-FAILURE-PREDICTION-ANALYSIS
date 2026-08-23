# Heart Failure Prediction Analysis

## 📌 Project Overview
This project explores the use of data analysis and machine learning techniques to investigate factors associated with the presence of heart disease. The project uses the Heart Failure Prediction Dataset from Kaggle. The dataset contains 918 observations, 11 predictor variables, and a binary target variable, HeartDisease.

## 🎯 Project Objective
The main objectives of this project are to: Understand the structure and quality of the dataset. Perform data preprocessing and cleaning. Apply feature engineering techniques. Conduct exploratory data analysis. Investigate relationships between clinical variables and heart disease. Perform statistical hypothesis testing. Analyze correlations and potential multicollinearity. Investigate outliers and feature distributions. Prepare the dataset for subsequent machine learning modeling. 

## 🎯 Technologies Used

Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Scikit-learn, Google Colab, GitHub 

## 📊 Dataset & Repository Structure
The dataset contains 918 observations, 11 predictor variables, and a binary target variable, HeartDisease.. To maintain a clean workflow, the project tracking files are organized as follows:
```text
├── data/
│   ├── raw/
│   │   └── heart_original.csv
│   ├── processed/
│   │   └── heart_disease_ml_ready.csv
│   └── models/
│       └── heart_disease_ml_ready.csv
├── notebooks/
│   └── ...
```

## 📊 Data Dictionary

### Original Dataset Variables

| Feature | Description | Type |
|---|---|---|
| **Age** | Patient age in years | Numerical |
| **Sex** | Patient sex | Categorical |
| **ChestPainType** | Type of chest pain | Categorical |
| **RestingBP** | Resting blood pressure | Numerical |
| **Cholesterol** | Serum cholesterol | Numerical |
| **FastingBS** | Fasting blood sugar indicator | Binary |
| **RestingECG** | Resting electrocardiogram result | Categorical |
| **MaxHR** | Maximum heart rate achieved | Numerical |
| **ExerciseAngina** | Exercise-induced angina | Binary |
| **Oldpeak** | ST depression | Numerical |
| **ST_Slope** | Slope of peak exercise ST segment | Categorical |
| **HeartDisease** | Target indicating presence of heart disease | Binary |

### Engineered Features

| Feature | Description | Type |
|---|---|---|
| **AgeGroup** | Age-based patient group | Categorical |
| **BP_Category** | Blood pressure category | Categorical |
| **Cholesterol_Risk** | Cholesterol risk category | Categorical |
| **MaxHR_Category** | Maximum heart rate category | Categorical |
| **Exercise_Stress** | Indicator combining exercise angina and Oldpeak | Binary |


## 🔎 Statistical Analysis

Statistical testing was incorporated to move beyond visual exploration and evaluate whether observed relationships were statistically significant.

The analysis includes:

- Independent-samples t-tests for selected numerical variables
- Chi-square tests of independence for categorical variables
- Effect-size analysis to assess the strength of categorical associations
- Correlation analysis for numerical variables

A significance level of α = 0.05 was used for hypothesis testing.


## ⚠️ Disclaimer
This project is intended for research and educational purposes only. The dataset and any machine-learning model developed from it should not be interpreted as a clinical diagnostic system. Real-world clinical use would require additional validation on representative patient populations, medical oversight, and evaluation of the model's safety, fairness, and reliability.

