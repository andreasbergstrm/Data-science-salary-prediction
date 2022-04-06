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

I looked at the distributions of the data and the value counts for the various categorical variables. Below is a highlight of the distribution of which sector data scientists in this sample works in.

![](sector_dist.png)

## Model Building

I tried three different models:
* XGBoosted Decision Tree Regression
* ...
* ...

![](feature_importance_xgb.png)

![](xgb_tree.png)

## Model Performance
