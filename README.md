
# Predicting if the Median Household of a Zip Code in the United States is Above/Under 49,000$

The goal of this project is creating a model which predict Median income per household (over/under $49,000) in US zip codes based on geography and social security payments.

As part of the process of building the model I conducted exploratory data analysis and produced visualizations using matplotlib and seaborn.
In order to choose the best model, Gridsearch and hyperparameter tuning were used for five classifiers: XGBoost, Random Forest, KNN, Logistic Regression and Decision Tree . Based on comparisons of the accuracy score,  XGBoost classifier was chosen for the final model.

Sources of Data:
US Census Report, Social Security Administration





## Data Cleaning and Merging
I worked with four different dataframes with more than 30,000 rows.

Issues I had to deal with:

-Duplication

-Small number of people in a zip code

-Null/Wrong values

My final data frame before feature ingeineering was a concatination of 4 tables and had 11,260 rows and 12 columns. 
I chose the number 49,000$  as my target over/under income, in order to get a relatively balanced numbers in the target value.

#### Values Count related to $49,000: Over - 47% , Under - 53%

One xample from my EDA - Household median and mean income per zip code has relatively normal distribution:
![dist](./images/read3.png)

## Features Engineering and Selection
After creating dummy variables and dropping columns with multicollinearity, the data frame had 68 columns. Accuracy Score for this data frame was : 0.547

My Next Steps Were:

-Creating Polynomials and Interactions (Total number of Columns: 2415)

-Scaling the Data with Sklearn StandardScaler

-Selection of best 50 features out of the 2415, using Sklearn SelectKBest (F regression).




Following is en axample of the hyper-parameter tunning for the XGBoost classifier:

<img src = "./images/image2.png" style = max width = 60%>


## Model Comparsion before and after Hyperparameter Tuning

<img src = "./images/image1.png"  width = 450  height = 220>
<img src = "./images/read1.png" style = max width = 70%>

The model with the best result after Hyperparameter Tuning  used the *XGBoost Classifier* and reached 0.733 Accuracy

<img src = "./images/read4.png" style = max width = 70%>



## Conclusions

It is chalenging and not very accurate to predict Income based only on Social Security payments and Geography in a zip code. Nevertheless, some general first impressions can be concluded:

-The State where the zip code is located has big influence, especially when dealing with ealthy or poor states (Connecticut and Puerto rico for example). 

-Some combinations of size of population and isolated places has an influence toward low income Prediction.

-High percentage of retired workers is sometime a sign for higher median income (probably because wealthy people move to specific areas after retirement).

-The number of people with disabilities has some influence to predict that the area has relativly lower incomes.


This is one example of a classifier feature importance( this one is from the logistic regression ):

<img src = "./images/read2.png">

## Future Development:

With additional data (for example tax collection) and with application on all the zip code in the US (this model include about one third of them) more acccura model can be built, based on similar methods that were used in this project.









