### 3rd Year Project Blog 2023/2024

*by Razvan Gorea and Sam Murphy*

### Introduction

This is a blog that goes through our developement journey of our 3rd Year Project. For some context, we decided on a web application, with the purpose being to help people find trails (hiking, walking and cycling) within the Republic of Ireland. We decided for the implementation to use React and Django. We planned to use the React web library to implement the user interface and the Django Python Framework to act as our server. Django would hold our trail data and then serve it to our React application when necessary. We knew we also wanted to integrate some of weather information via a weather API, as well as some additional pieces of information like points of interest which people could visit along their trail journeys. The weather information implementation would also be very important as it would help people plan ahead of time for their journeys. Preventing situations where a person goes on a trail and encounters bad weather. 

---

### Stage 1

This is our earliest stage of development. During this period we decided on what our major objectives would be in terms of features and functionality. At this point we also agreed on how to split up the workload. I (Razvan) would create the frontend features / user interface and Sam would create the backend functionality, mainly through parsing necessary json data. Then through the use of a Django REST API, custom endpoints would allow us to integrate the frontend with the backend. At this stage our biggest obstacles to overcome would be to figure out how to display the trail data and where we could get that kind of data to begin with. We concluded that we should both go off on our own, to conduct research and discover potential solutions.

---

### Stage 2

We have made substantial progress, I have discovered a library for React that allows the creation interactive maps, called React Leaflet. Sam also managed to find trail data from Sport Ireland. Sam managed to parse this data. His next task would then be to create speciifc endpoints with the Django REST Framework to allow me to start mapping the trails onto the react leaflet map. I have also decided to use OpenStreetMap for the tile layer. This would also simplify the creation of the map onto the webpage since I could import default styling, all provided by OpenStreetMap. My next task would be to figure out how to place markers onto the react leaflet map and what trail data is needed to make that possible. This would be a major step as it would open up the possibility of rendering markers for points of interest and the trails themselves.

---

### Stage 3

In this stage Sam created serializers and models for the trails and points of interest. With the endpoints, we managed to render many red markers onto the interactive map for points of interest. Unfortunely however we would soon encounter a minor problem. In order to place a marker on the react leaflet map, latitude and longitude coordinates are needed. The trail coordinates were swapped, to solve this issue we wrote a python script that took the trails json data and fixed it. Another problem we encountered was the geometry shapes that were created from the trails coordinates did not have lookup with trail data. The trail coordinates were simply a json array which had no connection or link to the rest of the trails data. To overcome this problem, a script was written to approximate the trails coordinates for every trail to the rest of the trails data. This was accomplished by approximating the coordinates, linking them and placing the new data into a CSV file. Then a new model was created `trailstoShape` which used the data from the CSV file.

---

### Stage 4

---

### Stage 5
