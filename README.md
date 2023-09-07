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
Use proxies of hilliness to test if hilliness affects station usage, such as determining the minimum and maximum elevations of venues within 100 meters and whether the station's elevation is higher or lower than the average elevation of nearby venues (average elevation delta).

## Results
Yelp provided over twice the number of venues returned for a 100-meter radius search compared to Foursquare. Hilliness was not found to be strongly correlated with the number of free bikes. This lack of correlation may be because the City Bike data represents only a snapshot of station usage. If users have a preference for riding downhill, over time, all bikes might end up at lower elevations. If such a preference exists, efforts should be made to transport bikes back to stations that are popular starting points, possibly using trailers or trucks.

## Challenges
One challenge was the imperfect measurement of hilliness. In reality, a 100-meter "as-the-crow-flies" radius may not accurately represent how users experience hilliness. Measuring the maximum and average inclinations along nearby bike routes would provide a better indicator. Obtaining this data remains a challenge. Another challenge was encountering rate limits with Yelp's daily requests, resulting in a dataset with only 500 stations instead of the full 524. Additionally, the USGS API occasionally returned errors when using the GET request function. To address this, I learned to save data files to CSV during each loop and then consolidate the data later from the CSV files.

## Future Goals
A future goal is to obtain a measure of station usage rather than just a snapshot of free bikes. This would require making periodic API requests to CityBikes and aggregating usage values.

