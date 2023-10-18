# Supervised Learning

## Project/Goals
The objective of this project was to used supervised learning techniques to build a machine learning model that can predict whether a patient has diabetes or not, based on certain diagnostic measurements.

## <br>Process
The project involved exploratory data analysis and pre-processing in which the imported ['diabetes.csv'](data/diabetes.csv) (obtained from [Kaggle](https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset/data)) dataset was analyzed and visualizations were created to examine the relationships between the different variables, handle outliers and incorrect values, standardize the features by scaling the data, and performing feature engineering as needed.

With the preliminary steps completed, we could then create machine learning model(s) we could then predict whether a patient has diabetes or not, using appropriate evaluation metrics such as accuracy, precision, and recall. Of the selected machine learning models, we wanted to ensure we have selected at least one ensemble model for our analysis to see how it performs. Any insights that are derived from this comparison could help make informed decisions based on the business questions asked.

## <br>Results
### EDA Process and Feature Engineering
- In this stage, we noticed outliers, an imbalance of data, and incorrect results. For example, the predictor variables 'Glucose', 'BloodPressure', 'SkinThickness', 'Insulin', and 'BMI' had zero values (which did not make sense in this context).
  - These outliers were handled two ways: removing zero value rows and/or replacing them with the median value.
- The data was also scaled due to the different unit representations and magnitudes. For instance, 'Pregnancies' would vary from 0 to 17, but 'Glucose' would vary from 0 (which was removed) to 199.
  - By scaling the features, we transform them to have a standard range, ensuring fair and effective contribution from all features during the learning process.
- As part of preprocessing we wanted to select only the relevant features (which were determined based on their correlation to the target variable 'Outcome') to help reduce model complexity, as well as improve its performance and interpretability.

### Training the Machine Learning Model
- We examined three machine learning models: logistic regression, support vector machines, and random forest classifiers.
  - The goal was to compare them and see how their performance varies.
- To compare the three models, we observed at:
  - Evaluation metrics: accuracy, precision, recall, F1-score, and ROC-AUC.
  - A ROC-AUC plot containing all three models.
  - Confusion matrices for all three models.
- Overall, SVM seemed to be the best-performing model for this particular binary classification task.
- We expected random forest classifier ensemble to be the best-performing model due to the nature of how ensemble methods produce their results; however, this was not the case.
  - This could be due to the assumptions made in the feature selection process, the lack of hyperparameter tunings, data imbalances not appropriately handled, and even the ensemble behaviour itself resulting from a lack of diversity which can impact its predictive power.

## <br>Challenges
- The time constraint limiting the feasibility of particular tasks.
- Determining how to handle the outliers/incorrect data/data imbalances.
- The most appropriate machine learning models to select for analysis.

## <br>Future Considerations
- Experiment with both approaches of using top correlated features as well as all features.
  - To examine the impact on model performance.
- Hyperparameter tuning to potentially improve the random forest ensemble performance.
- Implement other machine learning models such as XGBoost.
