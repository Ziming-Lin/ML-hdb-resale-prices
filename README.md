# HDB Resale Flat Prices and Machine Learning

## Machine Learning Objectives

- To discover patterns in HDB resale flat prices using common measures known to influence price
- Since the purchase price of individual units are not made publicly available, it is not possible to make ROI the subject of study
- Determine and compare the prediction accuracy of a multiple linear regression model to the popular XGBoost algorithm model


## Exploratory Data Analysis

<p align="center">
  <img width="800" height="800" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/pair_plot.png">  
</p>

<p align="center">
  <img width="400" height="400" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/displot_resale_date.png">
  <img width="400" height="400" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/displot_remaining_lease.png">
</p>

<p align="center">
  <img width="800" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/heatmap.png"> 
</p>

#### EDA Observations:

- COVID-19 severely impacted the market for 2 months and likely had an effect on resale prices
- Focus of study will be post-COVID-19 data
- Spikes in transactions can be observed every 3 months and is possibly due to to the way HDB's resale unit releases
keys to new BTO owners
- It is probable that many owners rush to sell their flats upon reaching the 5-year Minimum Occupation Period (MOP)




## Multiple Linear Regression Model

With RMSE of 63308 and mean percentage error of 10.82% on the training set, the model coefficients are given as:

#### Numerical Features

<p align="center">
  <img width="600" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/numerical_variables.png"> 
</p>

#### Categorical Features

<p align="center">
  <img width="300" height="250" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/flat_types.png"> 
  <img width="500" height="250" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/flat_models.png">
</p>

<p align="center">
  <img width="800" src="https://raw.githubusercontent.com/Ziming-Lin/ml-hdb-resale-prices/main/assets/station_names.png"> 
</p>


#### Model Interpretation:

- Resale Price = Model Intercept + Categorical Coefficients + Σ(Numerical Coefficient X Standard Scale Numerical Variable)
- Model intercept ($339,246) acts as baseline price
- From scale of coefficients, station name feature is usually the main price affecting factor
- While it seems that floor area is only slightly ahead of remaining lease feature, floor area should be grouped with flat type feature and assessed as flat size
- Feature importance is then:
> Flat Size > Remaining Lease > Unit Level > Distance to nearest MRT Station > Building Height


## XGBoost


