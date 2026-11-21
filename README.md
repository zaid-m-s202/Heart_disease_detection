# Heart Disease Detection Using Machine Learning

## Overview
This project focuses on building a machine learning model to classify whether a person is likely to have heart disease based on clinical attributes.

The project uses the **UCI Heart Disease dataset** and explores data preprocessing, exploratory data analysis, feature engineering, model training, and evaluation.

**Current status:** Initial Logistic Regression model developed. Further experimentation and model optimization are ongoing.

## Dataset
- **Source:** UCI Heart Disease Dataset
- **Target variable:** `num`
- **Classification:** Binary classification
  - `0` – No heart disease
  - `1` – Heart disease

The original target variable contains multiple severity levels (0–4). For this project, it is converted into a binary target, where values greater than 0 represent the presence of heart disease.

## Project Structure

```text
Heart-Disease-Detection/
│
├── dataset.csv
├── heart_disease_cleaned.csv
├── heart_disease_analysis.ipynb
├── heart_disease_logreg.joblib
├── metrics.json
├── requirements.txt
├── .gitignore
└── README.md
```

## Current Workflow

1. **Data Understanding:** Examining dataset structure, feature types, and missing values.
2. **Data Cleaning:** Handling invalid values and missing observations.
3. **Preprocessing:** Applying numerical imputation, feature scaling, categorical imputation, and one-hot encoding.
4. **Train-Test Split:** Splitting the data into training and testing sets using stratification.
5. **Model Development:** Training a Logistic Regression classifier.
6. **Model Evaluation:** Evaluating performance using accuracy, precision, recall, F1-score, ROC-AUC, and the confusion matrix.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Future Work

- Perform cross-validation to evaluate model stability.
- Investigate classification thresholds to improve sensitivity while controlling false positives.
- Implement and evaluate K-Nearest Neighbors (KNN).
- Compare multiple machine learning algorithms.
- Investigate feature importance and potential data leakage.
- Improve model performance and document limitations.

## Disclaimer

This project is developed for educational and machine learning experimentation purposes. It is not a clinically validated diagnostic tool and must not be used as a substitute for professional medical advice or diagnosis.