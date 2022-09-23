# World_Weather_Analysis
Identifying potential travel destinations and nearby hotels using OpenWeatherMap API, creating a travel itinerary, and a marker layer map using Google Maps Directions API.

## Overview of the analysis
The purpose of this project is to create the following:
  - Retrieve Weather Data of the nearest city of 2,000 random latitudes and longitudes
  - Create a customer travel destinations map based on user's weather preferences. The map includes potential travel destinations and nearby hotels shown on a marker layer map with pop-up markers.
  - Create a travel itinerary map that shows the route between four cities chosen from the customer’s possible travel destinations
  - Create a marker layer map with a pop-up marker for each city on the itinerary
  
## Results

### Deliverable 1 - Retrieve Weather Data
The code, which can be found in the Weather_Database folder, implements the following logic:
- Create a new set of 2,000 random latitudes and longitudes.
- Get the nearest city using the citipy module
- Perform an API call with the OpenWeatherMap.
- Retrieve the following information from the API call:
  * Latitude and longitude  
  * Maximum temperature
  * Percent humidity
  * Percent cloudiness
  * Wind speed
  * Weather description (for example, clouds, fog, light rain, clear sky)
- Add the data to a new DataFrame and export the DataFrame as a CSV file, and save it as WeatherPy_Database.csv in the Weather_Database folder

This is a snapshot of the weather data of cities:

![deliverable 1](https://user-images.githubusercontent.com/110554264/191998772-79d678cf-56d3-463b-986c-d97b32b0b952.png)

### Deliverable 2 - Create a customer travel destinations map
The code, which can be found in the Vacation_Search folder, implements the following logic:
- Import the WeatherPy_Database.csv file from Deliverable 1
- Prompt the user to enter their minimum and maximum temperature criteria for their vacation.
- Filter the city data for the temperature criteria. Determine if there are any empty rows, then drop them if necessary
- Create a hotel dataframe and search for a hotel for each city. Drop any rows in the hotel DataFrame where a hotel name is not found and export it as a CSV file

This is a snapshot of the hotel dataframe:

![deliverable 2](https://user-images.githubusercontent.com/110554264/192001829-bb767473-cbd3-48a9-bb32-eb4ed74662a7.png)
- Create a marker layer map that will have pop-up markers for each city on the map including city name, the country code, the weather description, and the maximum temperature.

Below is a snapshot of the marker layer map with marker popup:

![WeatherPy_vacation_map](https://user-images.githubusercontent.com/110554264/192003114-84eee15f-a09b-45a5-ad65-d7d52ad410d9.png)

### Deliverable 3 - Create a customer travel destinations map:
- Import the hotel dataframe which is extracted from Deliverable 2
- Create a marker layer map of the vacation search results
- Choose four cities that a customer might want to visit
- Create a directions layer map where the starting and ending city are the same city, the waypoints are the three other cities, and the travel_mode is "DRIVING

This is a snapshot of the directions layer map:

![WeatherPy_travel_map](https://user-images.githubusercontent.com/110554264/192004142-c270eb11-4988-4889-9c66-7a661dd72900.png)

- Create a new marker layer map of the cities on the travel route as below:

![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/110554264/192004276-8753df6e-c33f-430f-8c1e-8b0f77def234.png)


