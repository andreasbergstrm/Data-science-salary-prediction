# Data Science Salary Prediction: Project Overview

* (Basic Description)
* Cleaning/engineering
* Models used?
* Cross Validation?
* Results?

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

Feature engineering.  

I trained three different models and for performance evaluation I used three different metrics: Mean Squared Error, Root Mean Squared Error and Mean Absolute Error. Any model that does well in one metric is likely to do well in the others, but I wanted to compare the MSE performance which heavily punishes large individuals errors with more interpretable metrics such as RMSE and MAE.

The three models I used were:
* **Multiple Linear Regression** - A solid comparative baseline model.  
* **XGBoosted Decision Tree Regression** - Uses extreme gradient boosting to reduce bias and thus increase predictive performance.  
* **Lasso Regression** - Because of the sparse data from many categorical variables, I thought that the lasso regression would be effective.   

Cross-validation.  

Details of XGBoost.  

![](feature_importance_xgb.png)

![](xgb_tree.png)

## Model Performance

The XGBoosted Decision Tree Regression model was the best performer by far no matter the metric used including Root Mean Squared Error, which is expressed in terms of average salary per year in thousands of dollars.

* **XGBoosted Decision Tree Regression:** RMSE = 14.142  
* **Multiple Linear Regression:** RMSE = 17.666  
* **Lasso Regression:** RMSE = 19.580    
