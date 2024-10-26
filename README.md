# machine-learning
predict the mortality rate of patients with heart failure 

This project aims to predict the mortality of a patient who has heart failure using a clinical dataset, where the label death_event = 0 for not death and death_event = 1 for death. It can be categorized as a supervised machine learning approach, and specifically as a binary classification problem. 

## dataset
The dataset used in this project is sourced from Heart Failure Clinical Records Dataset which can be accessed at UCI Machine Learning Repository. 
https://doi.org/10.24432/C5Z89R

## model selection
Logistic Regression and Support Vector Classifier (SVC) 

## model validation
The dataset is split into 80% for training and validation sets and 20% for a test set using the train_test_split function from the Scikit-learn library. 
