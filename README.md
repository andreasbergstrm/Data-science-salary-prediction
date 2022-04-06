# Data Science Salary Prediction: Project Overview

* Built a machine learning model to predict average salary of data scientists in the US (RMSE ~ $14K), based on data from Glassdoor.
* Engineered features by creating new variables, using one-hot and numerical encoding for categorical variables and more.
* I built and compared three models: Multiple Linear, Lasso and XGBoosted Decision Tree regressions.
* Used GridSearchCV to optimize hyperparameters and reach the best model.

## Code and Resources Used

**Programming Language:** Python  
**Packages:** pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn, xgboost, graphviz  
**Dataset Source:** https://www.kaggle.com/datasets/nikhilbhathi/data-scientist-salary-us-glassdoor  

## Data Cleaning

The dataset contained many redundant and impractical variables which had to be dropped or transformed. There were also many missing data points that had to be dealt with via imputation or dropping variables with too much missing data.

## EDA

I looked at the distributions of the data and the value counts for the various categorical variables. Below is a highlight of the distribution of which sectors data scientists in this sample works in.

![](sector_dist.png)

## Model Building

First, I reconfigured some of the categorical variables by grouping together similar or uncommon categories within the different variables, thus creating larger and fewer groups within each variable. Then I checked the statistical significance of some of the technical skills employees had and dropped those who seemed to not be significantly associated with the average salary among data scientists. After that I created some new variables out of existing ones that I thought could help predict average salary.

Finally, I transformed the categorical variables with either one-hot encoding or numerical encoding depending on the number of categories within each variable. And before training the models I split the data into train and tests sets with a test size of 20%.

I trained three different models and for performance evaluation I used three different metrics: Mean Squared Error, Root Mean Squared Error and Mean Absolute Error. Any model that does well in one metric is likely to do well in the others, but I wanted to compare the MSE performance which heavily punishes large individuals errors with more interpretable metrics such as RMSE and MAE.

The three models I used were:
* **Multiple Linear Regression** - A solid comparative baseline model.  
* **XGBoosted Decision Tree Regression** - Uses extreme gradient boosting to reduce bias and thus increase predictive performance.  
* **Lasso Regression** - Because of the sparse data from many categorical variables, I thought that the lasso regression would be effective.   

For the XGBoosted model I used the grid search cross validation method to tune the hyperparameters and to reach the best model. Since the XGBoosted model also turned out to be the best performing model, I visualized the relative feature importance in that model and the resulting decision tree, as can be seen below.

![](feature_importance_xgb.png)

![](xgb_tree.png)

## Model Performance

The XGBoosted Decision Tree Regression model was the best performer by far no matter the metric used including Root Mean Squared Error, which is expressed in terms of average salary per year in thousands of dollars.

* **XGBoosted Decision Tree Regression:** RMSE = 14.142  
* **Multiple Linear Regression:** RMSE = 17.666  
* **Lasso Regression:** RMSE = 19.580    
