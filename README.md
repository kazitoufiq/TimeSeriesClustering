# Time Series Clustering

This github conatins the analytical model i developed to detect regular and irregular motor current profiles of point machines. 
Every point machine's swing, either Normal to Reverse or Reverse to Normal, is associated with motor current profile. The current value for every 10ms is captured by condition monitoring system. On an average, a swing has ~500 current values with 10ms interval. Hence, each swing can be considered as time sequence/time series. Using unsupervised machine learning, I've tried to detect regular and irregular motor current profiles of point machines. 




## Demo

[![](https://github.com/kazitoufiq/TimeSeriesClustering/blob/master/Demo_Outlier%20Detection.png)](https://indian-currency-prediction.herokuapp.com/)

## Overview


## Motivation

I  developed this model to detect regular and irregular motor current profiles of point machines. Every point machine's swing, either Normal to Reverse or Reverse to Normal, is associated with motor current profile. The current value for every 10ms is captured by condition monitoring system. On an average, a swing has ~500 current values with 10ms interval. Hence, each swing can be considered as time sequence/time series. Using unsupervised machine learning, I've tried to detect regular and irregular motor current profiles of point machines.

I was approached by one of my colleagues to help him to efficiently detect sub-optimal performance of point machines using the condition monitoring data. My colleague was spending a lot of time in observing current profiles and then defining threshold to detect abnormalities based on historical data while creating rules. The challenge was the current profiles vary not only from machine type(model) to machine type but also from machine to machine of same type(model) and there are around 1100 point machines in the network. 



## Technical Aspect

This asset analytic project can be divided into 5 parts:

1.	Accessing the backend SQL Server Database of the condition monitoring system and identifying all the relevant tables and columns using SQL query and getting a dump of the database and then uploading all the tables to a development SQL server. 

2.	Extracting historical motor current profile data for sample point machines using RODBC library from RStudio (R) (while necessary joins were done from dimension tables to enrich the data within RODBC)

3.	Transformation of current profile data from XML tag to tabular tall format was done in R using library data.table, stringr and dplyr. 
4.	Application of timeseries (considering each of the point machine’s swing as a timeseries) clustering using library dtwclust and applying shape-based distance metric and shape centroid (with cluster number, K=2) clustering method. The output of this step is a distance matrix where each distance value is a distance from the centroid the member belongs to.  

5.	Using empirical distance (for epsilon) value, applied density based DBSCAN clustering algorithm on distance matrix to automatically detect outlier (abnormal/anomaly)   

6.	Used Tableau to create an interactive dashboard to communicate the end result. 

A simplified version of the script can be found at my GitHub repo 

The demo dashboard is the outcome of this ML analytics model which can automatically detect any abnormal/sub-optimal performance of any Point Machine from its motor current profiles. The “red” legend represents any outlier/abnormal swing profile. The model also provides a sequence of abnormality trends over time (based on distance from cluster centroid) 



## Installation


## Run


## Credits
