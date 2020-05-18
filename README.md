# Time Series Clustering

This github conatins the analytical model i adopted to detect regular and irregular motor current profiles of point machines. 
Every point machine's swing, either Normal to Reverse or Reverse to Normal, is associated with motor current profiles. The current value for every 10ms is captured by condition monitoring system. On an average, a swing has ~500 current values with 10ms interval. Hence, each swing can be considered as time sequence/time series. Using unsupervised machine learning, I've tried to detect regular and irregular motor current profiles of point machines. 

