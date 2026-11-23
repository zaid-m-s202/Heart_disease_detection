# Heart Disease Detection Using Machine Learning

## Project Overview

This project implements and compares five supervised machine learning classification algorithms to predict the presence of heart disease using clinical attributes from the UCI Heart Disease Dataset.

The project covers data preprocessing, model training, hyperparameter tuning, cross-validation, performance evaluation, and model persistence.

**Project status:** Five machine learning models implemented and evaluated.

## Dataset

**Source:** UCI Heart Disease Dataset

- Total records: 920
- Original columns: 16
- Target variable: `num`
- Problem type: Binary classification
- Train-test split: 80:20, stratified

### Target Classification

| Value | Meaning |
|---|---|
| 0 | No heart disease |
| 1 | Presence of heart disease |

The original target was converted into binary labels using `num > 0`.

## Data Preprocessing

The preprocessing workflow includes:

- Removing the patient identifier (`id`) and excluding the dataset-source column.
- Handling invalid zero values in selected clinical measurements.
- Imputing missing numerical values using median imputation.
- Imputing missing categorical values.
- Encoding categorical variables using OneHotEncoder.
- Applying StandardScaler to numerical features for scale-sensitive algorithms.
- Using consistent training and testing partitions.

Preprocessing is integrated into scikit-learn pipelines to reduce data leakage.

## Machine Learning Models

Five classification algorithms have been implemented:

| Model | Configuration |
|---|---|
| Logistic Regression | Scaled numerical features and encoded categorical features |
| K-Nearest Neighbors | K = 16 |
| Decision Tree | Baseline DecisionTreeClassifier |
| Random Forest | 100 estimators, baseline configuration |
| Support Vector Machine | Tuned linear kernel, C = 0.1 |

### SVM Hyperparameter Tuning

SVM was optimized using GridSearchCV with five-fold stratified cross-validation.

Selected parameters:

- Kernel: Linear
- C: 0.1
- Cross-validation ROC-AUC: 0.8966

Final SVM test results:

| Metric | Value |
|---|---:|
| Accuracy | 0.8478 |
| ROC-AUC | 0.9132 |
| Class 1 Precision | 0.84 |
| Class 1 Recall | 0.90 |
| Class 1 F1-score | 0.87 |

## Model Evaluation

Models are evaluated using:

- Accuracy
- Precision
- Recall (Sensitivity)
- Specificity
- F1-score
- ROC-AUC
- Confusion Matrix
- Classification Report

Cross-validation is used to assess performance consistency and support model selection.

The consolidated results are stored in `reports/model_comparison.csv`.

## Project Structure

```text
HDD/
├── models/
│   ├── logistic_r_model.pkl
│   ├── heart_disease_knn.pkl
│   ├── decision_tree_model.pkl
│   ├── random_forest_model.pkl
│   └── svm_model.pkl
│
├── reports/
│   └── model_comparison.csv
│
├── notebooks/
│   ├── 01_logistic_regression.ipynb
│   ├── 02_knn_model.ipynb
│   ├── 03_decision_tree.ipynb
│   ├── 04_random_forest.ipynb
│   └── 05_svm_model.ipynb
│
├── preprocessing.py
├── heart_disease_uci.csv
├── heart_disease_cleaned.csv
└── README.md
```

*The structure represents the intended organization; exact notebook filenames may differ.*

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Joblib
- Jupyter Notebook

## Project Progress

- [x] Exploratory Data Analysis
- [x] Data Cleaning
- [x] Feature Preprocessing
- [x] Logistic Regression
- [x] KNN
- [x] Decision Tree
- [x] Random Forest
- [x] Support Vector Machine
- [x] SVM Hyperparameter Tuning
- [x] Model Evaluation
- [x] Cross-Validation
- [x] Model Persistence
- [x] Model Comparison Report

## Limitations

- The dataset contains missing clinical information and differences between contributing data sources.
- Results are based on a limited dataset and a single held-out test partition.
- The test set has been consulted during model development, so the reported results should not be interpreted as a fully independent external validation.
- Some clinical features may not be available during an initial patient assessment.
- Model predictions have not been clinically validated.

## Future Improvements

- Perform external validation on an independent dataset.
- Investigate feature selection and model interpretability.
- Evaluate probability calibration.
- Develop an interactive prediction interface.
- Improve reproducibility and deployment documentation.

## Disclaimer

This project is intended strictly for educational and research purposes. It is not a clinically validated medical diagnostic system and must not be used to make healthcare decisions.
