# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
Link between rental bike usage and the hilliness and/or elevation of stations in the San Francisco area. For this project usage will be approximated by free bikes at a given time, and free regular bikes (non-e-bikes) at a given time. 

## Process
#### Step 1 
get rental bike stations lat longs and station information including free_bikes, free e-bikes using city bike api
#### Step 2 
get all venues  within 100m of each bike station from both Yelp and Foursquare, scope of my project only includes venue ids and lat longs at this time
#### Step 3  
get elevation info from USGS API using lat longs from both yelp and citybike.
#### Step 4 
combine the dataframes using sqlite3 and use aggregate functions to get the range, and average of elevations of venues within  100m of a bike station
#### Step 5 
use the proxies of hilliness to test if hilliness affects station usage (min max of venues within 100m and whether the station elev is higher or lower than the average elev of nearby venues (avg_elev_delta)) 


## Results
Yelp had over twice the number of venues returned for a 100m radius search. Hilliness was not found to be strongly correlated with the number of free bikes, this may be because the city bike data only represents a time slice of station use. If there was a preference of users riding downhill only, then eventually all bikes would be at the lowest elevations. If there was a preference, workers must take bikes back to stations that are more popoular starting points using trailers/trucks.

## Challenges 
My meaurment of hilliness is imperfect  as in reality a radius of 100m "as the crow flies" is not how users would experience hilliness, rather the max and average inclination along nearby bike routes would be better. At point I am unsure how to get that data. Another challenge was using maxing out the yelp daily requests, and therefore having a slightly erroneous data set with only 500 stations rather than the full 524. The USGS API was also prone to returning errors using my get request function, I learned to save the data file to csv each loop, and then patch together data later from csvs 

## Future Goals
I would like to get a measure for usage of stations rather than a timeslice of free bikes. This would require making periodic api requests from citybikes and getting an aggregate usage value

# Final Project: Statistical Modeling with Python

## Project Goals
The goal of this project is to explore the relationship between rental bike usage and the hilliness and/or elevation of stations in the San Francisco area. For this project, usage will be approximated by the number of free bikes available at a given time and the number of free regular bikes (non-e-bikes) at a given time.

## Process
### Step 1: Obtain Rental Bike Stations' Latitude, Longitude, and Station Information
Retrieve rental bike stations' latitude, longitude, and station information, including the number of free bikes and free e-bikes, using the City Bike API.

### Step 2: Get Nearby Venues Data
Retrieve data for all venues located within 100 meters of each bike station from both Yelp and Foursquare. For the scope of this project, we will focus on venue IDs and latitude-longitude coordinates.

### Step 3: Obtain Elevation Information
Retrieve elevation information from the USGS API using latitude and longitude data obtained from both Yelp and CityBike.

### Step 4: Data Integration and Aggregation
Combine the dataframes using SQLite3 and apply aggregate functions to calculate the range and average of elevations of venues located within 100 meters of a bike station.

### Step 5: Analyze Hilliness
Use proxies of hilliness to test if hilliness affects station usage, such as determining the minimum and maximum elevations of venues within 100 meters and whether the station's elevation is higher or lower

