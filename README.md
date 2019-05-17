# mod_3_project
Predicting if the Median Household of a Zip Code in United States is Above/Under 49,000$

The goal of the model is trying to predict Median income per household (over/under $49,000) in US zip coded based on geographical data and social security payments 
Sources:
US Census Report, Social Security Administration

## Background
I worked with 4 different dataframes with more than 30,000 rows
Issues:
-Duplication
-Small number of people in a zip code
-Null/Wrong values
Final Data frame was a combination of 4 tables and had 11,260 rows and  12 columns. 
I chose the number 49,000$ in order the get a relatively balanced numbers in the target value.
Values Count: Over - 47% , Under - 53%

## Data Cleaning and Merging
After creating dummy variables and dropping columns with multicollinearity, data frame had 68 columns. Accuracy Score for this data frame was : 0.547
Next Steps:
-Creating Polynomials and Interactions (Total number of Columns: 2415)
-Scaling the Data with Sklearn StandardScaler
-Selection of best 50 features out of the 2415, using Sklearn SelectKBest (F regression).

## Features Engineering and Selection
It is complicated to predict Income based on Social Security payments and Geography in a zip code. Some general first impressions:
-The State where the zip code is located has big influence in the rich and poor areas (Connecticut and Puerto rico for example). 
-Some combinations of size of population and isolated places has an influence of low income Prediction.
- High percentage of retired workers is sometime a sign for higher median income (probably because people move to specific areas after retirement)
-Number of people with disabilities has some influence to predict an areas with lower incomes.

The model with the best result was the XGBoost model with 0.73 Accuracy


,,,
print('Improved Random Forest')
print('-------------------')
forest = RandomForestClassifier(bootstrap= True, max_depth= 100, max_features= 3, min_samples_leaf=3, min_samples_split= 12, n_estimators= 1000,n_jobs=-1)
forest.fit(X_train_scaled, y_train)
training_preds = forest.predict(X_train_scaled)
val_preds = forest.predict(X_test_scaled)
print_metrics(y_test, val_preds)
print('-------------------')
confusion = metrics.confusion_matrix(y_test, val_preds)
TP = confusion[1][1]
TN = confusion[0][0]
FP = confusion[0][1]
FN = confusion[1][0]

print ('True Positives:', TP)
print ('True Negatives:', TN)
print ('False Positives:', FP)
print ('False Negatives:', FN)
,,,

![read1] (https://github.com/omerhakim/mod_3_project/blob/master/images/read1.png)
