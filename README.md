# World_Weather_Analysis

## Purpose 

This repository provides an in-depth analysis on vacation plans based on weather around the world. This repository uses an OpenWeather API, Google Maps and Directions API, in addition to using the Citipy module as well as numerous other modules and packages. 


First, the numpy library was used to generate 2000 unique latitudes and longitudes. The idea behind gathering 2000 unique pairs is because 70% of the world is covered in ocean, so many coordinates may not equate to a nearby city. For this analysis, we wanted to make sure that weather was gathered for cities all over the globe. 

The CitiPy module was used to locate the nearest city to these generated coordinates. Now with an array of city names, the Open Weather API was used to gather relevant weather information for each city. The json objects were parsed and a Data Frame was created displaying all the information for each city. This Data Frame is titled WeatherPy_Database whihc is found in the Weather Database folder. 

The next step was to create a Vacation search so the user could define temperature ranges they want for the vacation destination. Based on the user's specifications, the WeatherPy_Database was filtered for the specific cities that match these specifications. The Google Places API was then used to find the closest hotel to each cities' coordinates. A Google Map was then created for every city and its relevant weather data, as well as the closest hotel. This file is titled WeatherPy_Vacation_Map which is found in the Vacation Search folder. This process was done so the user simply defines the preferred temperature of their desitnation and they are given an interactive Google Map of cities throughout the world that match their specification and provides relevant travel information. 


Finally, the last step in the analysis was to create a travel itinerary for the user. 4 cities were selected from the filtered Data Frame. Then using the Google Directions API, a Google Map was created showing travel directions for the trip including each stop on the trip. I choose to select a few cities in South Africa to show how the interactive map worked. A screenshot of this map can be found in the Vacation Itinerary Folder and is called WeatherPy_travel_map. Lastly, the neccesary weather and hotel information these 4 cities selected for the trip were then displayed on an additional Google Map for the users conveience. This is found in the same folder as the previous map and is called WeatherPy_Travel_map_markers.

After the completion of the analysis, any one could simply input the temperature they want for their vacation destination and these files will provide live weather information and relevant lodging for anywhere in the world mathcing your specifications. 
## Attachments

### Weather Data
  1. **Weather_Database.ipynb**  - creates dataframe of cities (citypy generated) based on randomly chosen Latitude and longitude (with numpy np.random) and connects to OpenWeather.com API's to collect and store current weather information by city
  2. **Weather_Database/WetherPy_Database.csv** - output csv from **Weather_Database.ipynb**

### Vacation Search
  1. **Vacation_Search.ipynb** - uses data from **Weather Data** to access google places API and chooses a hotel destination in the city specifed.  The hotel name was extracted from output JSON's and merged with the prior weather destination to create a new dataframe.  The hotel info dataframe data was used to create a google mpas output with markers that allow the user the abillity to click on an output destination based on desired vacation temperatures.  The result shows the hotel, city, country, and current weather.
  2. **Vacation_Search/WetherPy_vacations.csv** - output csv of dataframe with city, weather, location, and hotel information
  3. **Vacation_Search/Wether_vacation_map** - png of graphical google map output.

### Vacation Itinerary
  1.**Vacation_Itinerary.ipynb** - using google directions,**Vacation_Search/WetherPy_vacations.csv** was used and four destintations were chosen and seperated from the data frame.  Using google destinations a route was created between the four, and the weather information (as in **Vacation Search**) were inserted as markers for the destinations.
  2. **Vacation_Itinerary/WeatherPy_travel_map.png** - output google directions for 4 chosen cities
  3. **Vacation_Itinerary/WeatherPy_travel_map_Markers.png** - output google map with weather markers.
  