# Heart Disease Detection Using Machine Learning

## 1. Project Overview

This project focuses on developing and evaluating machine learning models to predict the presence of heart disease using clinical data.

The objective is to explore different classification algorithms, understand their performance, and compare their ability to distinguish between patients with and without heart disease.

This is an educational machine learning project and is not intended for clinical diagnosis.

## 2. Dataset

**Dataset:** UCI Heart Disease Dataset

- Original records: 920
- Original features: 16
- Target variable: `num`

The original target variable was converted into a binary classification problem:

- `0` – No heart disease
- `1` – Presence of heart disease

### Data preprocessing

The preprocessing workflow includes:

- Removing the patient identifier (`id`).
- Converting the target into binary classes.
- Handling invalid zero values in selected clinical features.
- Handling missing numerical and categorical values.
- Encoding categorical variables.
- Scaling numerical features where required.
- Splitting the dataset into training and testing sets using stratification.

## 3. Machine Learning Models

Three classification algorithms have been implemented.

### 1. Logistic Regression

- Used as the initial classification model.
- Numerical features were imputed and standardized.
- Categorical features were imputed and one-hot encoded.
- Evaluated using classification metrics and ROC-AUC.

### 2. K-Nearest Neighbors (KNN)

- Implemented using the KNN classification algorithm.
- Numerical feature scaling was applied because KNN is distance-based.
- Hyperparameter exploration was performed to select the number of neighbors.
- Final model: KNN with K = 16.
- Evaluated using classification metrics and ROC-AUC.

### 3. Decision Tree

- Implemented using `DecisionTreeClassifier`.
- Numerical scaling was not required.
- Missing values were imputed and categorical features were one-hot encoded.
- Evaluated using classification metrics.
- Five-fold stratified cross-validation was performed using ROC-AUC.

## 4. Model Evaluation

The models are evaluated using the following metrics:

| Metric | Purpose |
|---|---|
| Accuracy | Overall prediction correctness |
| Precision | Correctness of positive predictions |
| Recall | Ability to identify positive cases |
| Specificity | Ability to identify negative cases |
| F1 Score | Balance between precision and recall |
| ROC-AUC | Ability to distinguish between the two classes |

A common held-out test set is used to compare all three models.

Five-fold stratified cross-validation is also used to assess Decision Tree performance and consistency.

## 5. Project Structure

```text
HDD/
│
├── models/
│   ├── logistic_r_model.pkl
│   ├── knn_model.pkl
│   └── decision_tree_model.pkl
│
├── reports/
│   └── model_comparison.csv
│
├── notebooks/
│   ├── 01_logistic_regression.ipynb
│   ├── 02_knn_model.ipynb
│   └── 03_decision_tree.ipynb
│
├── heart_disease_uci.csv
├── heart_disease_cleaned.csv
├── preprocessing.py
└── README.md
```

*Note: Filenames and folder contents may vary as the project evolves.*

## 6. Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Jupyter Notebook

## 7. Current Project Progress

- [x] Dataset exploration
- [x] Data cleaning and preprocessing
- [x] Binary target conversion
- [x] Logistic Regression implementation
- [x] KNN implementation and K selection
- [x] Decision Tree implementation
- [x] Five-fold cross-validation for Decision Tree
- [x] Model evaluation and comparison
- [x] Saving trained models
- [x] Saving model comparison report

## 8. Future Work

- Implement Random Forest.
- Implement Support Vector Machine (SVM).
- Compare all models using consistent evaluation metrics.
- Perform further model optimization.
- Analyze feature importance and model interpretability.
- Identify the most suitable model based on evaluation results.

## 9. Disclaimer

This project is developed for educational and machine learning practice purposes. Its predictions should not be used as a substitute for professional medical advice, diagnosis, or treatment.
