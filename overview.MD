# Why Analyzing the Data?

Airbnb is an online marketplace for arranging or offering lodging, primarily homestays, or tourism experiences since 2008. NYC is the most populous city in the United States and also one of the most popular tourism and business place in the world. The data contains listing activity and metrics.

The main objective for the analysis is to understand how different aspects influence the price, such as the location, reviews, and what makes a host more or less popular. Also we want to recommend a reasonable price for its users, in case those users are going to list proprieties to be rented at their platform. All of this could help providing a better user experience for a wide range of customer groups.

In this project we've explored some of the common features for each of the listings and learnt what makes a listing have a higher price or not. Also we've applied some machine learning techniques in order to predict the price based on those features. The results, in terms of R^2 score, showed that the GBT Regressor model has a slight advantage over Random Forest Regressor. Also, we cans also check that the results using the text feature are a bit better than both GBT and RF without this feature.


# Dataset Fields

These are the main features on the dataset.

* listing ID : name of the listing
* name: description of the listing
* neighbourhood_group: to which neighbourhood group in new york does the listing belong to
* latitude coordinates/longitude coordinates: coordinates value of the listing
* room_type: what is the kind of room
* price: wat is the cost of the listing


# EDA

## Univariate Analysis 

### Neighbourhood Group
We can see that Manhattan, Brooklyn and Queens, respectively, have the most number of listings on NYC

<img src="https://drive.google.com/uc?id=1zYGamH4F5RCRTUllbaSnZCyr0E_9-_zz">


### Room Type

From this we can see that there are three types of rooms: Entire Home/Apt, Private Room, Shared Room. We can also see that there are a lot of missing values and weird labels. Entire home/apt represent more than a half of the listings. The second most frequent is the Private Room. Customers seem to prize for comfort and privacy, which can also be confirmed by the few number of listings with shared rooms.

<img src="https://drive.google.com/uc?id=1Z1iXc0WcV_RHoFIIfs9y83IOtzTqpFHG">

### Minimum Nights
Most of the hosts require 20~35 days of staying. This could be related to the high number of entire home/apt and private rooms on the listings.
<img src="https://drive.google.com/uc?id=1pyygA7U4d0Pe32Ka-XCPfXX_XqLCwteJ">
