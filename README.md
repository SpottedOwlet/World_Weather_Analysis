<h2> <p align=center>World Weather Analysis</p> </h2>

<h3>Background & Purpose: </h3>
This analysis is to aid the operation of PlanMyTrip, which is a top travel comapny that specializes in the internet related services in the hotel & lodging sector. This project is an example of how current weather data coupled with google maps platform could be utilized to effectively create detailed travel plans and itineraries.

<h3> Resources: </h3>
Technologies & Software: Jupyter Notebook, Pandas, CitiPy, Python Requests, APIs, JSON Traversals.

<h3> Analysis Overview: </h3>
The Analysis for this project requires a long series of operations. For simplicity and functionality purposes, the analysis is broken into three parts. 

- Creation of Weather Database
- Searching for datapoints based on User Criteria
- Creation of Itinirary & Travel map

Let us discuss these in detail:

<h3> Creation of Weather Database: </h3>

The initial database is created using numpy, citipy module and openweather API. Random pairs of latitues and longitudes are generated using np.random.uniform() function. Then nearby city search is performed using CityPy module in Python. At the same time, the corresponding weather data for the cities is obtained using Python requests & OpenWeather API. The city and corresponding weather data is added to the database. This database is then extracted and stored as a csv file for further use.

<h4><p align=center>  Weather Database for Nearby Cities </p></h4>
<p align=center><kbd><img width="753" alt="Screen Shot 2021-12-01 at 10 55 32 PM" src="https://user-images.githubusercontent.com/90424752/144372959-9ce2fda9-fee0-472a-b261-0bfbab33bbe4.png"></kbd>  </p>


<h3> Searching for Datapoints Based on User Criteria </h3>
In this step, the csv file stored in the earlier step is imported into the python environment and loaded into a dataframe. The user input is taken for user's weather preference for the vacation destinations. As per the user preference, the dataframe is then filtered to have the only destinations that satisfy the user criteria. Using nearby search, a hotel in each city is added to the our dataframe. The cities for which hotel is not found, are skipped and removed from the dataframe. The clean dataframe is then used to display resulting cities based on user criteria. The vacation search results are displayed using google map APIs as shown below. The location markers show the destination cities from the cleaned dataframe. 

<h4><p align=center> Cleaned Hotel DataFrame </p></h4>
<p align=center><kbd>
  <img width="749" alt="Screen Shot 2021-12-01 at 11 41 50 PM" src="https://user-images.githubusercontent.com/90424752/144378770-69d99238-67fa-4add-9424-419c7260bbe9.png">
  </p></kbd>


<h4><p align=center> Vacation Map Satisfying User Criteria </p></h4>
<p align=center><kbd><img width="1028" alt="WeatherPy_vacation_map" src="https://user-images.githubusercontent.com/90424752/144374149-f36d599d-9271-48e2-9ca7-9d4fbed5e930.png"></kbd></p>


<h3>  Creation of Itinerary & Travel map </h3>
This is the final step of the analysis where the possible itineraries are displayed along with the travel map as shown below. The travel map layer is added using google direction APIs and importing gmaps package.

<h4><p align=center> One of the Suggested Travel Itinerary Map</p> </h4>
<p align=center><kbd><img width="1023" alt="WeatherPy_travel_map" src="https://user-images.githubusercontent.com/90424752/144374250-14495c97-0817-4be0-a8c3-84338e2ecfa7.png"></kbd></p>

<h4><p align=center> Destination Markers for One of the Suggested Travel Itinerary Map</p></h4>
<p align=center><kbd><img width="1680" alt="WeatherPy_travel_map_markers" src="https://user-images.githubusercontent.com/90424752/144379893-564c2dff-f986-4c10-af4d-57d8445d43a8.png"></kbd></p>

<h4>Limitation:</h4>

- The limitation for travel directions_layer is that, it only shows the travel route for 'DRIVING', 'BICYCLING' or 'WALKING' mode of transport. Waypoints are not supported when the travel mode is 'TRANSIT' (this is a limitation of the Google Maps directions service).
- The user preferance is limited to weather only. The parameters such as trip duration, country of preference, mode of transport between the cities, accommodation preference are not included in this analysis.
- Not all possible city options are included due to algorithm used to generate latitudes and logitudes. The analysis could be modified to include the cities of interest and then location, weather and accomodation data can be gathered as per city preference.
