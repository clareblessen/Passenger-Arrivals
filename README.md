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
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/volume_by_city.jpeg">
</p>
When looking at the data on on average basis across all cities, we can see a clear upward trend and seasonality, with winter being an unpopular time to travel, and summer a popular time.
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/total_activity.jpeg">
</p>
In a closer look at monthly volume, summer shows the greatest amount of travel, especially July and August, and winter the least, despite an expectation that holidays might increase travel in December.
<p align="center">
  <img width="800" height="600" src="https://github.com/clareblessen/Passenger-Arrivals/blob/master/Images/monthly_boxplot.jpeg">
</p>
