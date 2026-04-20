# Customer-Churn-Analysis-Prediction(Telco Dataset)

## Project Overview

This project focuses on predicting customer churn using machine learning. The goal is to identify customers who are likely to leave a telecom service based on their demographic, account, and usage data.

The model is trained on the Telco Customer Churn dataset and uses a Random Forest Classifier to achieve reliable prediction performance.

## Objectives
Perform data cleaning and preprocessing
Convert categorical data into numerical format
Train a machine learning model to predict churn
Evaluate model performance using accuracy and confusion matrix
## Dataset Information
Total Records: 7043 customers
Features: 21 columns
Target Variable: Churn (Yes/No)
Key Features:
Customer demographics (gender, senior citizen, dependents)
Account details (tenure, contract type, billing)
Services used (internet, streaming, support)
Charges (monthly and total charges)
## Technologies Used
Python
Pandas, NumPy
Scikit-learn
Matplotlib
## Data Preprocessing
## Handling Data Types
Converted TotalCharges from object → numeric
Filled missing values using median
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')
df['TotalCharges'] = df['TotalCharges'].fillna(df['TotalCharges'].median())
## Encoding Categorical Variables
Used Label Encoding for categorical features
from sklearn.preprocessing import LabelEncoder
labelencoder = LabelEncoder()

for col in categorical_cols:
    df[col] = labelencoder.fit_transform(df[col])
## Model Building
## Train-Test Split
80% Training
20% Testing
from sklearn.model_selection import train_test_split
## Feature Scaling
Applied StandardScaler
from sklearn.preprocessing import StandardScaler
## Model Used
Random Forest Classifier
from sklearn.ensemble import RandomForestClassifier
rf = RandomForestClassifier()
rf.fit(X_train, y_train)
## Model Performance
Accuracy: 0.78 (78%)
## Confusion Matrix
Visualized using ConfusionMatrixDisplay
Helps understand:
True Positives (Correct churn predictions)
False Positives
False Negatives
True Negatives
## Key Insights
Customers with month-to-month contracts are more likely to churn
Higher monthly charges increase churn probability
Lack of tech support and online security correlates with churn
## Notes
Fixed Pandas warning by avoiding chained assignment
Used median imputation for missing values in TotalCharges
## Future Improvements
Hyperparameter tuning (GridSearchCV)
Try advanced models (XGBoost, LightGBM)
Deploy model using Flask or Streamlit
Add feature importance visualization
