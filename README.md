
# Predicting if the Median Household of a Zip Code in the United States is Above/Under 49,000$

## Background
The goal of the model is trying to predict Median income per household (over/under $49,000) in US zip codes based on geographical data and social security payments 

Sources of Data:
US Census Report, Social Security Administration

## Data Cleaning and Merging
I worked with 4 different dataframes with more than 30,000 rows

Issues I had to deal with:

-Duplication

-Small number of people in a zip code

-Null/Wrong values

My final data frame was a combination of 4 tables and had 11,260 rows and  12 columns. 
I chose the number 49,000$ in order to get a relatively balanced numbers in the target value.
#### Values Count: Over - 47% , Under - 53%

## Features Engineering and Selection
After creating dummy variables and dropping columns with multicollinearity, data frame had 68 columns. Accuracy Score for this data frame was : 0.547

My Next Steps Were:

-Creating Polynomials and Interactions (Total number of Columns: 2415)

-Scaling the Data with Sklearn StandardScaler

-Selection of best 50 features out of the 2415, using Sklearn SelectKBest (F regression).

## Model Comparsion before and after Hyperparameter Tuning


![read1](https://github.com/omerhakim/mod_3_project/blob/master/images/read1.png)

The model with the best result after Hyperparameter Tuning was the *XGBoost Classifier with 0.73 Accuracy*

![boost](https://github.com/omerhakim/mod_3_project/blob/master/images/Screen%20Shot%202019-05-17%20at%202.21.40%20PM.png)



## Conclusions
It is complicated to predict Income based on Social Security payments and Geography in a zip code. Some general first impressions:
-The State where the zip code is located has big influence in the rich and poor areas (Connecticut and Puerto rico for example). 
-Some combinations of size of population and isolated places has an influence of low income Prediction.
- High percentage of retired workers is sometime a sign for higher median income (probably because people move to specific areas after retirement)
-Number of people with disabilities has some influence to predict an areas with lower incomes.







