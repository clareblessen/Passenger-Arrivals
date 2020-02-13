# Travel Trends & Forecasting

## The Question
Travel (via flights) appears to be increasing in popularity, and certain destinations seem to explode overnight. 

Does this increase in travel really exist, and can it inform us on future trends?

## The Data
I downloaded monthly passenger volume for the U.S. and 16 cities abroad from various bureaus of transportation. To look at exogenous variables, I then obtained weather data over time for each location from the Meteostat API, the cost of living index for each city over time from Numbeo.com, and population data for each location over time from WorldPopulationReview.com. 
<p align="center">
  <img width="900" height="500" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/world_map.jpg">
</p>

## EDA
Every city evidenced very similar shape and seasonal trends: the differences lie in the magnitude and intercept.
<p align="center">
  <img width="700" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/volume_by_city.jpeg">
</p>
When looking at the data on on average basis across all cities, we can see a clear upward trend and seasonality, with winter being an unpopular time to travel, and summer a popular time.
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/total_activity.jpeg">
</p>
In a closer look at monthly volume, summer shows the greatest amount of travel, especially July and August, and winter the least, despite an expectation that holidays might increase travel in December.
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/monthly_boxplot.jpeg">
</p>
I was interested in looking at which destinations had the largest overall increases in visitors from 2010-2018.
<p align="center">
  <img width="900" height="500" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/largest_increases.jpg">
</p>

## Anomaly Analysis
I performed anomaly analysis over the data for each city in an attempt to identify which cities saw unexpected increases or decreases in traveler volume. Using Facebook Prophet to model the trend at a 90% confidence interval, we see the shaded confidence interval around our actual data. The model’s assumption is that in the future we will see similar trend changes as the history, or in other words, the trend will continue at the same trajectory. Based on this assumption, we can identify points where the actual data reached a level that would be considered outside of the expected trend with 90% confidence, which I identified as anomalies. The analysis for Reykjavik, Iceland, can be seen below:
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/iceland_anomalies.jpeg">
</p>
From the graph, it's clear that there was a spike in tourists 2010-2012 that continued until it began to decrease in 2018. There was also a spike in activity in Winter 2017, which could warrant further investigation.

## Forecasting
Finally, I attempted to forecast activity for the next three years. A SARIMA model offered the best results, with an rmse of 1,934,568
compared to Facebook Prophet's rmse of 2,114,279. The SARIMA model utilized differencing of 1 (month) to stationarize the trend, and 12 (months=1 year) to stationarize the seasonality.

Using my exogenous variables of temperature, precipitation, cost of living index, and population of a city did not improve my model, but rather completely threw off the predictions. While weather does fluctuate in accordance with seasonality, it does not affect the popularity of a destination, most likely due to the fact that vacations are planned based on expected weather rather than changes in weather. My thinking in including cost of living index as a predictor was that a decrease in the expense of a destination might trigger increased tourism, however this proved generally untrue. Population also appeared to not be predictive of flight passenger arrival activity, despite an increased population theoretically leading to an increase in travelers returning home to that destination. My hypothesis is that both cost of living index and population did not vary enough over this time period to have much predictive value.
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/future_image.jpeg">
</p>

## Dash Dashboard
I created a dashboard to visualize each 

## Implications & Future Studies
Tourism is one of the largest economic drivers across the globe. By observing trends early on and identifying what is driving growth, economies can prepare for increased volume and businesses can know where to invest their capital as it relates to marketing, hotels, airlines, and all other facets of the tourism industry. 

Moving forward, identifying what outside factors drive these trends would allow for much greater implications in regards to predicting economic growth due to tourism in these destinations. Without other predictive variables, this model will always be reacting to observed trends as opposed to predicting them. I would be interested to look at the relationship between social media activity related to a location and an increase in its popularity, particularly casual inference as it relates to content by "influencers" or celebrities.





