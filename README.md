# Predicting Mortality of Patients with Heart Failure

## Project Overview
This project applies machine learning to predict mortality in patients with heart failure, based on their clinical data. By accurately predicting patient outcomes, this project aims to support better treatment decisions and improve survival rates. We explore different machine learning models to identify patterns in patient data that are difficult to capture through traditional methods, ultimately helping to refine medical predictions.

## Contents
1. [Introduction](#introduction)
2. [Problem Setup](#problem-setup)
3. [Data and Methods](#data-and-methods)
4. [Results and Model Evaluation](#results-and-model-evaluation)
5. [Conclusion and Future Work](#conclusion-and-future-work)
6. [References](#references)

## 1. Introduction
Heart failure is a serious condition that affects millions worldwide. It occurs when the heart can’t pump blood effectively, leading to symptoms like fatigue, breathlessness, and fluid buildup. While the prognosis can vary greatly, certain clinical factors can help predict a patient's risk of mortality. This project uses machine learning to analyze these factors and improve the accuracy of these predictions.

## 2. Problem Setup
Our goal is to predict whether a patient with heart failure will survive or pass away. This is a **binary classification task**:
- **Labels**: 0 = survived, 1 = deceased
- **Features**: Clinical variables like age, blood pressure, and ejection fraction (percentage of blood leaving the heart per contraction).
  
The dataset, obtained from the UCI Machine Learning Repository [1], includes 299 patient records with 12 clinical features.

## 3. Data and Methods

### 3.1 Data Preprocessing and Feature Selection
We start by preprocessing the data. Since the dataset has no missing values, we focus on scaling continuous features (like age and serum creatinine) to improve model performance. After scaling, we perform feature selection based on correlation analysis to retain the most impactful features, including age, ejection fraction, serum creatinine, serum sodium, and time.

### 3.2 Model Selection
We evaluate two primary models:
1. **Logistic Regression**: A simple yet effective model for binary classification, well-suited for healthcare applications due to its interpretability. We tune parameters like regularization (C), penalty type, and solver to maximize validation accuracy.
2. **Support Vector Classifier (SVC)**: Known for handling binary classification tasks with complex decision boundaries. SVC works by maximizing the margin between classes. We tune parameters including the regularization (C), kernel type, and gamma for optimal results.

We split the data into 80% for training/validation and 20% for testing. For model validation, we use 4-fold cross-validation to avoid overfitting and get a more accurate performance assessment.

## 4. Results and Model Evaluation
The models performed as follows:

| Model                | Training Error | Validation Error | Validation Accuracy | Test Error |
|----------------------|----------------|------------------|---------------------|------------|
| Logistic Regression  | 0.4081         | 0.4433          | 81.97%             | 0.5105     |
| Support Vector Classifier (SVC) | 0.3290 | 0.6623 | 20.50% | 0.6371 |

Logistic Regression had higher accuracy and lower validation error compared to SVC. While SVC fit the training data well, it struggled with validation data, likely due to overfitting caused by the dataset’s small size. The results suggest that **Logistic Regression** is the better model for this prediction task, offering a balance between simplicity and accuracy.

## 5. Conclusion and Future Work
This project shows that Logistic Regression effectively predicts heart failure mortality with an accuracy of approximately 82%. Important factors influencing mortality include age, ejection fraction, serum creatinine, serum sodium, and time. Interventions focusing on improving heart function and managing follow-up care could positively impact patient outcomes.

While our model performs reasonably well, the small dataset poses limitations. Future work could involve:
- Expanding the dataset with more patient records.
- Additional clinical features (like lifestyle and mental health data) to improve predictions.
- Testing more advanced machine learning models to capture complex patterns in larger datasets better.

## 6. References
[1] Heart Failure Clinical Records Dataset. UCI Machine Learning Repository. https://doi.org/10.24432/C5Z89R
