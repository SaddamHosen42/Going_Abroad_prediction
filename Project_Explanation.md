# Abroad Study Outcome Prediction

## Overview
This machine learning project focuses on predicting the outcome of an abroad study application (positive or negative) based on students' demographic, academic, and performance-related features. The complete workflow follows standard machine learning practices, including data loading, preprocessing, model training, evaluation, and comparison.

---

## Table of Contents
1. [Data Loading](#1-data-loading)
2. [Data Preprocessing](#2-data-preprocessing)
3. [Data Splitting](#3-data-splitting)
4. [Model Building and Evaluation](#4-model-building-and-evaluation)
5. [Model Comparison](#5-model-comparison)
6. [Visualization of Model Performance](#6-visualization-of-model-performance)
7. [Final Decision](#7-final-decision)

---

## 1. Data Loading
The dataset was loaded from a CSV file hosted on GitHub using the `pandas` library. An initial inspection was conducted to understand:
- Dataset dimensions
- Column names
- Data types
- Presence of missing values

This step ensured familiarity with the dataset structure before proceeding to preprocessing.

---

## 2. Data Preprocessing
Data preprocessing was performed to prepare the dataset for effective model training.

### 2.1 Checking for Missing Values
The dataset was examined for null values using built-in pandas functions. It was observed that **no missing values** were present, so no imputation was required.

### 2.2 Data Type Verification
The `dataset.info()` method was used to verify:
- Correct data types
- Non-null counts for each column

This confirmed the overall quality and consistency of the dataset.

### 2.3 Encoding Categorical Variables
Since machine learning models require numerical input:
- The **Gender** column was encoded into numerical form using `LabelEncoder`.
- The target variable **Abroad_result** (positive/negative) was encoded into a new column `Abroad_result_encoded`, where:
  - `0` represents **negative**
  - `1` represents **positive**
- The original categorical target column was then removed to avoid redundancy.

### 2.4 Feature Scaling
To ensure all numerical features contribute equally to the learning process and to avoid bias due to differing scales, `StandardScaler` was applied. This transformation standardizes features to:
- **Mean = 0**
- **Standard deviation = 1**

Feature scaling is particularly important for models such as Linear and Logistic Regression.

---

## 3. Data Splitting
The dataset was divided into:
- **Features (X)**: All independent variables (Age, Gender, Feature columns, etc.)
- **Target (y)**: `Abroad_result_encoded`

The data was then split into training and testing sets using `train_test_split`:
- **Training set**: 80%
- **Testing set**: 20%
- `random_state = 100` was used to ensure reproducibility.

---

## 4. Model Building and Evaluation
Three different machine learning models were implemented and evaluated to compare their performance.

### 4.1 Random Forest Classifier
**Training:**
A Random Forest Classifier was initialized with:
- `n_estimators = 100`
- `random_state = 100`

The model was trained on the training dataset.

**Prediction:**
Predictions were generated for both training and testing datasets.

**Evaluation:**
The model was evaluated using:
- Accuracy
- Precision
- Recall
- F1-score

The Random Forest achieved an exceptionally high training accuracy (≈ **99.8%**), indicating excellent learning of training data. However, its test accuracy (≈ **75%**) was noticeably lower, suggesting **overfitting**, a common issue with ensemble models when not tuned.

### 4.2 Linear Regression
**Training:**
Although Linear Regression is primarily designed for continuous output, it was included for comparison purposes. The model was trained using the training dataset.

**Prediction & Binary Conversion:**
Linear Regression produces continuous outputs. To adapt it for binary classification:
- A threshold of **0.5** was applied.
- Predictions above 0.5 were classified as `1` (positive).
- Predictions of 0.5 or below were classified as `0` (negative).

**Evaluation:**
After conversion to binary form, classification metrics were calculated. The model achieved:
- Training accuracy ≈ **75.9%**
- Test accuracy ≈ **72.8%**

This demonstrates reasonable but limited suitability for classification tasks.

### 4.3 Logistic Regression
**Training:**
Logistic Regression, which is inherently designed for binary classification, was trained using the same training dataset with `random_state = 100`.

**Prediction:**
Binary predictions were obtained directly without requiring threshold conversion.

**Evaluation:**
The model achieved:
- Training accuracy ≈ **76.1%**
- Test accuracy ≈ **72.8%**

Logistic Regression showed stable and consistent performance between training and test sets, indicating better generalization.

---

## 5. Model Comparison
A comparative DataFrame was created to summarize the performance of all three models across:
- Accuracy
- Precision
- Recall
- F1-score

for both training and testing datasets.

### Observations
- **Random Forest** performed best on training data but showed signs of overfitting.
- **Linear Regression** and **Logistic Regression** showed similar and more consistent performance across training and testing sets.
- **Logistic Regression** demonstrated better theoretical suitability for the classification task.

---

## 6. Visualization of Model Performance

### 6.1 Model Comparison Plot
Bar plots were created to visually compare performance metrics across all models. These plots provide an intuitive overview of model strengths and weaknesses.

### 6.2 Confusion Matrices
Confusion matrices were generated for each model on the test dataset, highlighting:
- **True Positives (TP)**
- **True Negatives (TN)**
- **False Positives (FP)**
- **False Negatives (FN)**

These matrices helped analyze the types of errors made by each model.

### 6.3 ROC Curves and AUC
ROC curves were plotted to evaluate the classification performance across different thresholds. The AUC scores obtained were:
- **Random Forest**: 0.67
- **Linear Regression**: 0.63
- **Logistic Regression**: 0.63

An AUC closer to 1 indicates better class separation, while 0.5 represents random guessing. The ROC analysis provided additional insight beyond accuracy alone.

---

## 7. Final Decision
Although **Random Forest** achieved the highest training performance, it showed signs of **overfitting**. 

**Logistic Regression** demonstrated stable and consistent results across training and testing datasets and is inherently suitable for binary classification. 

###Therefore, **Logistic Regression** is selected as the final and comparatively better model for this project.



## Author
SaddamHosen42
