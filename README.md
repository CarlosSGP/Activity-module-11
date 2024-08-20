# Activity-module-11

Introduction
This is an analysis of about 78K car sales in the US. With information on the make, model, mechanical differences and specifications, color, and the region it is in, we want to determine what particular features of the car are stronger predictors for the price.

The Business Problem
Our goal is to determine what particular features of the car are stronger predictors for the price. The data we are using contains different features which are both numerical (odometer tally, year, number of cylinders) and categorical (condition, type of car, manufacturer). There are also features that may have no relationship to the price at all (VIN, state, paint color). With so much data at hand, we need to determine which of these features help us properly predict car prices and which ones are less useful and so we should not include them in the training of our model. 

Preparing the Data
We will remove columns of data that we do not believe will have an impact on price. This was an iterative process as we looked at what our MSE and R2 is for the model as we tweaked which features to use. The features we are removing are 'VIN','id','region','state','model', and'paint_color'.

Data Analysis

Features Used
The following features were used to predict the price of the car:

year
manufacturer
condition
cylinders
fuel
odometer
title_status
transmission
drive
size
type

For the categorical features, we used label encoding to convert them to numerical values.

Model Selection

We performed a cross validation between 3 different models (Linear, Lasso and Ridge). They all performed very similar, with the Linear regression having the lowest MSE by a very small margin. We considered the models to be relatively good at predicting with an R2 of 29.
46%

Linear Regression: Cross-validation RMSE = 10372.8179
Best Ridge: {'alpha': 10.0}, RMSE = 10374.2858
Best Lasso: {'alpha': 1.0}, RMSE = 10374.2859

Evaluate the best models on the test set
Linear Regression: RMSE = 10493.0477, R2 = 0.2946
Ridge: RMSE = 10493.0757, R2 = 0.2946
Lasso: RMSE = 10493.0662, R2 = 0.2946

Model Evaluation

The best model was the Linear Regression model with a 104993.0477 MSE and a 0.2946 R2. We can also look at the coefficients for each feature for Linear regression as follows:

Linear Regression Coefficients:
year             363.693970
manufacturer      18.855220
condition         75.212238
cylinders       2553.935106
fuel           -5995.367777
odometer          -0.008133
title_status    -249.363372
transmission    3491.518990
drive           -865.213268
size            -235.095838
type               8.807758


Further, when we look at feature importance on the Linear model, we get a sense of which features are more relevant to predicting the price.

![image](https://github.com/user-attachments/assets/86e036f7-2434-4651-954e-1ae4d0c852c7)


We can see that the year is positively correlated. The fuel type is negatively correlated which means types like diesel and electric cars are more expensive. The cylinders are positively correlated which means the more cylinders the car has, the higher the price. 

Conclusion
The three most important features for predicting the price of a car are the year, fuel type, and cylinders. The year and cylinders are positively correlated with the price, while the fuel type is negatively correlated. This means that newer cars are more expensive, while diesel and electric cars are more expensive than gas cars. The number of cylinders in the car also affects the price, with more cylinders leading to a higher price. 
