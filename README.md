Introduction:
New York City (NYC), also known as The Big Apple, is the most populous city in the United States situated on one of the world’s largest natural harbors. Every Year many people from different parts of the world move to New York to. This brings us to a question: Which Neighborhood should one choose to settle down in this city of dreams? To answer this question, a person does a lot of research about all the neighborhoods and tries to get maximum details possible before making any decision so that they don’t end up wasting their time and money.

New York City is composed of five boroughs: Brooklyn, Queens, Manhattan, The Bronx and Staten Island. Many Districts and landmarks in NYC are well known.

In this article we will explore the neighborhoods in all these five boroughs of New York City and the most common venue categories in each neighborhoods such as park, hotel, bakery, coffee shop and so on. We will then cluster the neighborhoods using k-means clustering so that it becomes easy to determine for a person as to which neighborhood they should choose for their move in to this big city.

K-Mean Clustering:
Wikipedia: k-means clustering is a method of vector quantization, originally from signal processing, that aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean (cluster centers or cluster centroid), serving as a prototype of the cluster.


K-Means is a type of partitioning clustering, that is, it divides the data into K non-overlapping subsets or clusters without any cluster internal structure or labels. This means, it’s an unsupervised algorithm. Objects within a cluster are very similar, and objects across different clusters are very different or dissimilar.

Data Acquisition and Cleaning:
Neighborhood has a total of 5 boroughs and 306 neighborhoods. In order to segment the neighborhoods and explore them, we will essentially need a dataset that contains the 5 boroughs and the neighborhoods that exist in each borough as well as the the latitude and longitude coordinates of each neighborhood.

Data Sources:
The New York neighborhood dataset was obtained from https://cocl.us/new_york_dataset.

The geographical coordinates of new york neighborhoods were obtained using https://geo.nyu.edu/catalog/nyu_2451_34572
