
# Predicting if the Median Household of a Zip Code in the United States is Above/Under 49,000$

The goal of this project is creating a model which predict Median income per household (over/under $49,000) in US zip codes based on geography and social security payments.

As part of the process of building the model I conducted exploratory data analysis and produced visualizations using matplotlib and seaborn.
In order to choose the best model Gridsearch and hyperparameter tuning were used. Based on the results, I decided to utilize XGBoost classifier for the final model.

Sources of Data:
US Census Report, Social Security Administration





## Data Cleaning and Merging
I worked with 4 different dataframes with more than 30,000 rows

Issues I had to deal with:

-Duplication

-Small number of people in a zip code

-Null/Wrong values

My final data frame was a combination of 4 tables and had 11,260 rows and  12 columns. 
I chose the number 49,000$  as my target over/under income, in order to get a relatively balanced numbers in the target value.

#### Values Count related to $49,000: Over - 47% , Under - 53%

![dist](./images/read3.png)

## Features Engineering and Selection
After creating dummy variables and dropping columns with multicollinearity, the data frame had 68 columns. Accuracy Score for this data frame was : 0.547

My Next Steps Were:

-Creating Polynomials and Interactions (Total number of Columns: 2415)

-Scaling the Data with Sklearn StandardScaler

-Selection of best 50 features out of the 2415, using Sklearn SelectKBest (F regression).

Example from my EDA - Household median and mean income per zip code has relatively normal distribution
<img src = "./images/image2.png" style = max width = 60%>


## Model Comparsion before and after Hyperparameter Tuning

<img src = "./images/image1.png"  width = 450  height = 220>
A

<img src = "./images/read1.png">

The model with the best result after Hyperparameter Tuning was the *XGBoost Classifier with 0.73 Accuracy*

<img src = "./images/read4.png" style = max width = 70%>



## Conclusions
It is complicated to predict Income based on Social Security payments and Geography in a zip code.

Some general first impressions:

-The State where the zip code is located has big influence in the significantly rich and poor areas (Connecticut and Puerto rico for example). 

-Some combinations of size of population and isolated places has an influence for low income Prediction.

-High percentage of retired workers is sometime a sign for higher median income (probably because people move to specific areas after retirement).

-The number of people with disabilities has some influence to predict an areas with lower incomes.


<img src = "./images/read2.png">







