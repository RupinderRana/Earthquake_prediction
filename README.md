# Earthquake_prediction
## Overview
Countless dollars and entire scientific careers have been dedicated to predicting where and when the next big earthquake will strike. But unlike weather forecasting, which has significantly improved with the use of better satellites and more powerful mathematical models, earthquake prediction has been marred by repeated failure due to highly uncertain conditions of earth and its surroundings. Now, with the help of artificial intelligence, a growing number of scientists say changes in the way they can analyze massive amounts of seismic data can help them better understand earthquakes, anticipate how they will behave, and provide quicker and more accurate early warnings. This helps in hazzard assessments for many builders and real estate business for infrastructure planning from business perspective. Also many lives can be saved through early warning. This project aims a simple solution to above problem by predicting or forecasting likely places to have earthquake in next 7 days. 
## Dataset
Real time data that updates every minute on https://earthquake.usgs.gov/earthquakes/feed/v1.0/csv.php for past 30 days. 

* time ---------------------- Time when the event occurred. Times are reported in milliseconds since the epoch
* latitude ------------------- Decimal degrees latitude. Negative values for southern latitudes.
* longitude ------------------ Decimal degrees longitude. Negative values for western longitudes.
* depth ---------------------- Depth of the event in kilometers.
* mag ------------------------ Magnitude of event occured.
* magType -------------------- The method or algorithm used to calculate the preferred magnitude
* nst ------------------------ The total number of seismic stations used to determine earthquake location.
* gap ------------------------ The largest azimuthal gap between azimuthally adjacent stations (in degrees).
* dmin ----------------------- Horizontal distance from the epicenter to the nearest station (in degrees).
* rms ------------------------ The root-mean-square (RMS) travel time residual, in sec, using all weights.
* nnet ------------------------- The ID of a data source contributor for event occured.
* id -------------------------- A unique identifier for the event.
* types ----------------------- A comma-separated list of product types associated to this event.
* place ----------------------- named geographic region near to the event.
* type ------------------------ Type of seismic event.
* locationSource -------------- The network that originally authored the reported location of this event.
* magSource ------------------- Network that originally authored the reported magnitude for this event.
* horizontalError ------------- Uncertainty of reported location of the event in kilometers.
* depthError ------------------ The depth error, three principal errors on a vertical line.
* magError -------------------- Uncertainty of reported magnitude of the event.
* magNst ---------------------- The total number of seismic stations to calculate the magnitude of earthquake.
* status ---------------------- Indicates whether the event has been reviewed by a human.

## Model implementation and methodology
After preprocessing with removing null values, and feature engineering as discussed above, I performed Boosting algorithms for classification problem.

Adaboost classifier with estimator as DecisionTreeClassifier

Adaboost classifier with estimator as RandomForestClassifier

 Xgboost algorithm.

## Improvement and conclusion
Though XGboost model has given Higher roc_auc and better recall, I believe any work given always has some scope for improvement and in here we could also use RNN or LSTM for time series or rather event series forecasting. LSTMs have hidden memory cells that help in remembering and handeling time series or event series data well. Moreover for xgboost I have just used hyper parameters from already tuned Adaboost models, but we can also tune xgboost hyper parameter and find best parameters using GridSearchCV or RandomSearch.
