# World_Weather_Analysis
Module 6 - Python Modules and APIs
- NumPy
- Citipy
- Openweathermap.org current weather API
- Google places and directions APIs
## Overview
### Weather_Database
World_Weather_Analysis uses the NumPy module to generate 2000 random latitudes and longitudes, followed by the Citipy module to find the nearest city for those coordinates.

The OpenWeatherMap API is used to request current weather for those randomly generated cities.   (https://openweathermap.org/current)

The JSON from the openweathermap/current endpoint is parsed to create a Pandas DataFrame combining weather information with city data.  This data is saved and exported to /Weather_Database/WeatherPy_Database.csv

### Vacation_Search
In Vacation_Search.ipynb, the WeatherPy_Database.csv generated in Weather_Database is used as the data source.

Two input statements prompt the user to enter their minimum and maximum temperature for their ideal vacation (with some error handling for non-numeric values).

A new Pandas DataFrame is created based on the temperature filter, containing only cities with a current max temperature within the ideal temperature range.

Finally a call to Google Places API is made to find the nearest hotel for these vacation cities.

Any rows with null or empty strings are removed and a dataFrame of cities, city weather, and hotel name are saved and exported to /Vacation_search/WeatherPy_vacation.csv.   

A marker layer map is created with maps to display the cities and hotel information.
![CityMap](/Vacation_Search/WeatherPy_vacation_map.png)

### Vacation_Itinerary 🇳🇿
In Vacation_Itinerary.ipynb, Google Directions API is used to create a travel itinerary between four cities in New Zealand chosen from the WeatherPY_vacation.csv.
![Itinerary](/Vacation_Itinerary/WeatherPy_travel_map.png)
