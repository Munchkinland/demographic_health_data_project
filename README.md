![image](https://github.com/Munchkinland/demographic_health_data_project/assets/92251234/0929f6cd-add2-4ed0-abec-ed9966719cfa)

Chronic Kidney Disease Prediction
Justification
After thorough analysis of the provided dataframe and data dictionary available here, our project aims to predict the occurrence of Chronic Kidney Disease (CKD). We believe that the dataset is sufficiently representative to leverage linear regression techniques for this prediction.

1. Quick Exploratory Data Analysis (EDA)
1.1 Info about the Dataset

The dataset contains 3140 entries and 108 columns.
Data types include float64, int64, and object.
Memory usage is 2.6+ MB.
1.2 Standardization of Numeric Variables

Standardization is performed on numeric variables using the StandardScaler from scikit-learn.
A new DataFrame called total_data_scal is created, containing the scaled numeric variables and the original "CKD_number" column.
2. Feature Selection
2.1 Reduce and Split the Data

The dataset is split into predictor variables (X) and the target variable (y).
Training and testing sets (X_train, X_test, y_train, y_test) are created using train_test_split.
Feature selection is performed using SelectKBest with the F-regression score function.
30% of the features are selected.
2.2 Generation of Train and Test Split in CSV

Selected features and target variable columns are concatenated and saved as CSV files for training and testing sets.
2.3 Joining X_train_sel and X_test_sel Data Sets

The training and testing sets with selected features are concatenated into a new DataFrame called total_data.
3. Correlation Analysis
3.1 Correlation Matrix (All Values)

A correlation matrix for all variables in total_data is calculated and visualized using seaborn heatmap.
3.2 Correlation Matrix (Top 15 Values)

The top 15 variables with the highest correlation with the target variable ("CKD_number") are visualized in a heatmap.
4. Linear Regression
4.1 Load Data and Split into Train and Test Sets

The data is split into training and testing sets for a linear regression model.
4.2 Model Training

A logistic regression model is trained on the training data.
4.3 Obtaining Intercept and Coefficients

The intercept and coefficients of the logistic regression model are obtained and displayed.
4.4 Model Prediction

The trained model is used to make predictions on the test set (y_pred).
Additional Note
The warning about convergence in logistic regression is shown, suggesting potential issues that might be addressed by increasing the number of iterations or scaling the data.
Overall, this code appears to cover various aspects of data preprocessing, feature selection, and linear regression modeling, with a focus on logistic regression for predicting the "CKD_number" target variable. If you have specific questions or if there's anything specific you'd like assistance with, feel free to ask!

Chronic Kidney Disease is a medical condition characterized by the gradual deterioration of kidney function over an extended period. The kidneys play a crucial role in filtering blood, removing waste and excess fluids, and producing urine. When affected by chronic kidney disease, these vital functions can deteriorate gradually.

The disease is classified into stages based on the glomerular filtration rate (GFR), ranging from stage 1 (kidney damage with normal or increased GFR) to stage 5 (very low GFR, indicative of advanced kidney failure).

Causes of Chronic Kidney Disease
Diabetes: Both Type 1 and Type 2 diabetes can contribute to kidney damage.
High Blood Pressure: Hypertension is a major risk factor for kidney disease.
Glomerulonephritis: Inflammation of the kidney's filtering units (glomeruli).
Interstitial Nephritis: Inflammation of the kidney tubules and surrounding structures.
Polycystic Kidney Disease: Hereditary kidney diseases leading to cyst formation.
Urinary Tract Obstruction: Prolonged obstruction due to conditions like prostate enlargement, kidney stones, and certain cancers.
Vesicoureteral Reflux: Causes urine to flow back into the kidneys.
Recurrent Kidney Infection (Pyelonephritis): Frequent kidney infections.
Risk Factors
Factors increasing the risk of chronic kidney disease include:

Diabetes
High Blood Pressure
Cardiovascular Disease
Smoking habit
Obesity
Ethnicity (Black, Native American, or Asian American descent)
Family history of kidney disease
Abnormal kidney structure
Advanced age
Frequent use of medications damaging the kidneys
Exploratory Data Analysis (EDA)
Our analysis involved thorough Exploratory Data Analysis (EDA) to understand the relationships within the dataset. This included:

Correlation Analysis: Understanding the relationships between different variables, especially with respect to the target variable (CKD).
Feature Selection: Employing techniques like SelectKBest to identify the most relevant features for prediction.
Linear Regression and Model Optimization
We utilized Linear Regression as the baseline model to predict CKD occurrence. To enhance the model's performance and handle potential overfitting, we implemented Lasso Regression. This regularization technique helps in feature selection and prevents over-reliance on specific variables.

Model Training and Evaluation
The model was trained on a subset of the data, and performance was evaluated using metrics such as Mean Squared Error (MSE) and R2 Score. The optimal regularization strength (alpha) for the Lasso model was determined through a systematic search.

Model Persistence
The final optimized Lasso Regression model was saved using the pickle library for future use and deployment.

Importance of Early Detection
Early detection is crucial, especially for individuals with risk factors like diabetes or hypertension. Regular check-ups can identify chronic kidney disease in its early stages, allowing for interventions to slow its progression. Management strategies include dietary changes, blood pressure and glucose control, and specific medical treatments. In advanced stages, therapies like dialysis or kidney transplantation may be necessary.

