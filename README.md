# Patient Health Risk Prediction

## Introduction
This project aims to predict whether a patient is "At Risk" (1) or "Healthy" (0) based on clinical and demographic features. Using a systematic AI pipeline, we automate the risk assessment process to support healthcare decision-making.

## Problem Statement
The objective is to build a binary classification model that accurately identifies high-risk patients. Given the clinical importance of not missing at-risk cases, we prioritize the **F1-Score** as our primary success metric to balance precision and recall.

## Dataset Description
The dataset consists of approximately 3,000 patient records.
- **Features**: Clinical metrics such as Jaundice levels, Heart Rate, BMI, Age (in days), and Oxygen Saturation.
- **Target Variable**: `risk_level` (0 = Healthy, 1 = At Risk).
- **Processing**: Categorical variables like 'Gender' were encoded, and numerical features were standardized using `StandardScaler`.

## Methodology
The project is divided into a 10-step pipeline across multiple notebooks:
1. **Data Cleaning (`data_cleaning.ipynb`)**: Handled missing values and removed duplicates.
2. **EDA (`analysis.ipynb`)**: Visualized feature distributions and correlation heatmaps to identify top predictors.
3. **Preprocessing (`preprocessing.ipynb`)**: Performed feature scaling and train-test splitting (80/20 ratio).
4. **Modeling (`modeling.ipynb`)**: Implemented 3 Machine Learning models (Logistic Regression, Random Forest, XGBoost) and 1 Deep Learning model (ANN).
5. **Optimization**: Used Hyperparameter tuning to refine model performance.

## Results
Based on our evaluation on the test set:
| Model | Accuracy | F1-Score |
| :--- | :--- | :--- |
| **XGBoost** | **99.8%** | **0.993** |
| Random Forest | 99.3% | 0.971 |
| Logistic Regression | 89.6% | 0.544 |
| ANN (Deep Learning) | ~98.5% | (Variable) |

## Conclusion
XGBoost emerged as the superior model for this tabular dataset. Future work involves testing the model on external datasets to ensure generalizability across different hospital systems.
