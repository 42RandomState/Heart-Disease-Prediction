# Heart Disease Prediction Project

**Author:** Leonardo Cofone

## Overview

This project aims to analyze and predict heart disease presence using a dataset containing various medical features of patients. The goal is to build a machine learning model capable of predicting the probability of heart disease onset, potentially supporting early diagnosis in clinical practice.

## Dataset

The dataset contains 1025 samples, each with 13 explanatory variables and one binary target variable (`target`) indicating presence (1) or absence (0) of heart disease.

Key features include:
- `age`: patient age
- `sex`: gender (1 = male, 0 = female)
- `cp`: chest pain type
- `trestbps`: resting blood pressure
- `chol`: serum cholesterol
- `fbs`: fasting blood sugar
- `restecg`: resting electrocardiographic results
- `thalach`: maximum heart rate achieved
- `exang`: exercise induced angina
- `oldpeak`: ST depression induced by exercise relative to rest
- `slope`: slope of the peak exercise ST segment
- `ca`: number of major vessels colored by fluoroscopy
- `thal`: thalassemia
- `target`: heart disease presence (1) or absence (0)


## Project Structure

### 1. Initial Data Analysis

- Data import and preview
- Dataset info and descriptive statistics
- Identification of categorical and numerical variables
- Detection of skewness in numerical features
- Visualization of data distributions

### 2. Data Preprocessing

- Dataset split into training (80%) and test (20%) sets with stratification on target variable
- Missing value imputation using median strategy
- Logarithmic transformation on highly skewed numerical features
- Standard scaling of numerical variables
- Construction of a preprocessing pipeline for consistent transformations

### 3. Classification Models

Multiple classification algorithms were trained and evaluated:

- Logistic Regression
- Random Forest Classifier
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Gradient Boosting Classifier

For each model:

- Training with 3-fold cross-validation
- Evaluation using confusion matrices, precision, recall, and F1-score
- Performance comparison based on F1-score

### 4. Best Model Selection

- Random Forest Classifier showed the best performance with an F1-score around 0.96
- Hyperparameter tuning performed via GridSearchCV to optimize:
  - Number of estimators
  - Maximum depth
  - Minimum samples split
  - Minimum samples leaf
  - Bootstrap option

Best parameters found:
- `bootstrap=False`
- `max_depth=None`
- `min_samples_leaf=1`
- `min_samples_split=2`
- `n_estimators=100`

### 5. Final Model Evaluation

- The optimized Random Forest model was trained on the entire training set and tested on the unseen test set.
- Achieved perfect classification metrics on the test set (precision, recall, F1-score = 1.0), with no indication of overfitting.
- Verified balanced class distributions and no overlap between training and test sets.


## Evaluation Metrics

- **Precision:** The ratio of true positive predictions to all positive predictions.
- **Recall:** The ratio of true positive predictions to all actual positives.
- **F1-score:** The harmonic mean of precision and recall.
- **Confusion Matrix:** Summarizes true positives, false positives, true negatives, and false negatives.

## Conclusions

- The Random Forest classifier with optimized hyperparameters achieved excellent performance for heart disease prediction.
- The preprocessing pipeline efficiently handles skewed features and missing data.
- The final model is reliable and free from overfitting, showing promise as a clinical decision support tool.

---

If you have any questions or want to suggest improvements, feel free to contact me.
Thank you
