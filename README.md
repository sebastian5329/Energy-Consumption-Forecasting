# energy-consumption-forecasting
This project focuses on forecasting energy consumption by comparing the performance of traditional time series models with machine learning approaches (Tree based models, XGBoost). The objective is to accurately predict future demand to support grid management and load balancing decisions.

## Workflow
1. *Data Cleaning & EDA*
   - Removed duplicates and missing values.
   - Checked skewness and checked outliers using the IQR and capped them using Winsorization method.
   - Converted the date column to DateTime and set it as the index.
   
2. *Feature Engineering*
   - Extracted Year, Month, Week, Day, Hour, etc.
   - Visualized trends and seasonality using STL decomposition.
   - Seasonal subseries plots by month and hour.

3. *Stationarity & Time Series Models*
   - Checked stationarity using *ADF* and *KPSS* tests.
   - Applied differencing where needed.
   - Built ARIMA, SARIMA, and Auto ARIMA models (parameters via ACF/PACF).
   - Tried Prophet for trend-seasonality modeling.

4. *Machine Learning Models*
   - Linear Regression, Decision Tree, Random Forest, XGBoost.
   - Hyperparameter tuning with RandomizedSearchCV.

## Results
The best time series model was Prophet and reached a Mean Absolute Error of 188 and Root Mean Square Error of around 245, with an R² score of about 0.20.  
Switching to machine learning improved the results significantly — XGBoost brought the MAE down to 99, RMSE to 136, and explained 78% of the variance in the data.

## Tech Stack
- *Python*
- *Data Analysis*: pandas, numpy
- *Visualization*: matplotlib, seaborn
- *Time Series*: statsmodels, prophet
- *Machine Learning*: scikit-learn, xgboost
- *Statistical Tests and math*:scipy
