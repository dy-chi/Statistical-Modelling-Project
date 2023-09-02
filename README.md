# Final Project: Statistical Modeling with Python

## Project Goals
The goal of this project is to explore the relationship between rental bike usage and the hilliness and/or elevation of stations in the San Francisco area. For this project, usage will be approximated by the number of free bikes available at a given time and the number of free regular bikes (non-e-bikes) at a given time.

## Process
### Step 1: Obtain Rental Bike Stations' Latitude, Longitude, and Station Information
Retrieve rental bike stations' latitude, longitude, and station information, including the number of free bikes and free e-bikes, using the City Bike API.

### Step 2: Get Nearby Venues Data
Retrieve data for all venues located within 100 meters of each bike station from both Yelp and Foursquare. For the scope of this project, I will only take venue IDs and latitude-longitude coordinates, and not further details of venues.

### Step 3: Obtain Elevation Information
Retrieve elevation information from the USGS API using latitude and longitude data obtained from both Yelp and CityBike.

### Step 4: Data Integration and Aggregation
Combine the dataframes using SQLite3 and apply aggregate functions to calculate the range and average of elevations of venues located within 100 meters of a bike station.

### Step 5: Analyze Hilliness
Use proxies of hilliness to test if hilliness affects station usage, such as determining the minimum and maximum elevations of venues within 100 meters and whether the station's elevation is higher or lower than this average

