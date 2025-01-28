Introduction:
New York City (NYC), also known as The Big Apple, is the most populous city in the United States situated on one of the world’s largest natural harbors. Every Year many people from different parts of the world move to New York to. This brings us to a question: Which Neighborhood should one choose to settle down in this city of dreams? To answer this question, a person does a lot of research about all the neighborhoods and tries to get maximum details possible before making any decision so that they don’t end up wasting their time and money.

New York City is composed of five boroughs: Brooklyn, Queens, Manhattan, The Bronx and Staten Island. Many Districts and landmarks in NYC are well known.

In this article we will explore the neighborhoods in all these five boroughs of New York City and the most common venue categories in each neighborhoods such as park, hotel, bakery, coffee shop and so on. We will then cluster the neighborhoods using k-means clustering so that it becomes easy to determine for a person as to which neighborhood they should choose for their move in to this big city.

K-Means Clustering:
K-Means clustering is a method of vector quantization, originally from signal processing, that aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean (cluster centers or cluster centroid), serving as a prototype of the cluster.


K-Means is a type of partitioning clustering, that is, it divides the data into K non-overlapping subsets or clusters without any cluster internal structure or labels. This means, it’s an unsupervised algorithm. Objects within a cluster are very similar, and objects across different clusters are very different or dissimilar.

Data Acquisition and Cleaning:
Neighborhood has a total of 5 boroughs and 306 neighborhoods. In order to segment the neighborhoods and explore them, we will essentially need a dataset that contains the 5 boroughs and the neighborhoods that exist in each borough as well as the the latitude and longitude coordinates of each neighborhood.

Data Sources:
The New York neighborhood dataset was obtained from https://cocl.us/new_york_dataset.

The geographical coordinates of new york neighborhoods were obtained using https://geo.nyu.edu/catalog/nyu_2451_34572




---------------------<br><br><br>



New York City Dataset
Link: https://geo.nyu.edu/catalog/nyu_2451_34572

This New York City Neighborhood Names point file was created as a guide to New York City’s neighborhoods that appear on the web resource, ‘New York: A City of Neighborhoods.’ Best estimates of label centroids were established at a 1:1,000 scale, but are ideally viewed at a 1:50,000 scale. This dataset will provide the addresses of neighborhood of NYC in json format. An extract of the json is as follows:


Foursquare API
Link: https://developer.foursquare.com/docs

Foursquare API, a location data provider, will be used to make RESTful API calls to retrieve data about venues in different neighborhoods. This is the link to Foursquare Venue Category Hierarchy. Venues retrieved from all the neighborhoods are categorized broadly into ‘Arts & Entertainment’, ‘College & University’, ‘Event’, ‘Food’, ‘Nightlife Spot’, ‘Outdoors & Recreation’, etc. An extract of an API call is as follows:


Methodology
Download and Explore New York City Dataset
In order to segment the neighborhoods of New York City, a dataset is required that contains the 5 boroughs and the neighborhoods, that exist in each borough, with respective latitude and longitude coordinates. This dataset is downloaded using the mentioned URL.

Once the .json file is downloaded, it is analyzed to understand the structure of the file. A python dictionary is returned by the URL and all the relevant data is found to be in the features key, which is basically a list of the neighborhoods. The dictionary is transformed, into a pandas dataframe, by looping through the data and filling the dataframe rows one at a time.

As a result, a dataframe is created with Borough, Neighborhood, Latitude and Longitude details of the New York City’s neighborhood.


Upon analysis, it is found that the dataframe consists of 5 boroughs and 306 neighborhoods.

Further, ‘geopy’ library is used to get the latitude and longitude values of New York City, which was returned to be Latitude: 40.71, Longitude: -74.01.

The curated dataframe is then used to visualize by creating a map of New York City with neighborhoods superimposed on top. The following depiction is a map generated using python ‘folium’ library.


RESTful API Calls to Foursquare
The Foursquare API is used to explore the neighborhoods and segment them. To access the API, ‘CLIENT_ID’, ‘CLIENT_SECRET’ and ‘VERSION’ is defined.

There are many endpoints available on Foursquare for various GET requests. But, to explore the cuisines, it is required that all the venues extracted are from ‘Food’ category. Foursquare Venue Category Hierarchy is retrieved and returned request is further analyzed.

Upon analysis, it is found that there are 10 major or parent categories of venues, under which all the other sub-categories are included.

As said earlier, the ‘FOOD’ category is the matter of interest. A function is created to return a dictionary with ‘Category ID’ & ‘Category Name’ of ‘Food’ & it’s sub-categories.
