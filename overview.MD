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

* <a href="https://github.com/dimitriarthur/AIRBNB-Data-Analysis/tree/main/Data%20Analysis%20Artifacts" target="_blank"> Full EDA Here</a>


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

### Price Analysis
The price paid for each location lies between 0 and 300 dolars, mostly. We can see that higher prices are way less frequent on the listings, specially above a thousand dollars.

<img src="https://drive.google.com/uc?id=1yPHp26QZW0nQHtMDslHAdpab3N9n4gww">


### Number of Reviews
Most of the hosts are kind of unknown, having few reviews, with 0 to 50 being the most frequent range.

<img src="https://drive.google.com/uc?id=1j9-Q2WdQbFJnHOWG1Ly9h3HvdF0YQqj1">


### Availability_365

Most of the hosts are available during a short period of the year, from 0 to 50 days. The second most frequent period availability is next to 365 days, in other words the whole year

<img src="https://drive.google.com/uc?id=1DtLXUoBFXn_DBzbtGyVcB-G6O-c6BAPc">


## Bivariate Analysis

### Popular Neighbourhood Groups and Price
Here we are analyzing the neighbourhood groups that, together, represent 97% of the listings (Manhattan, Queens and Brooklyn).

We can see that:

* From the boxplots and barplots, Manhattan has the highest mean price, followed by Brooklyn and Queens.
* Manhattan's mean price is almost the double of Queen's mean price
* There are a lot of outliers, that is, the price vary a lot in each neighbourhood group.

<img src="https://drive.google.com/uc?id=1JpFZ7b1UEld4QHpdmpFvJYErXZgvnjbV">

<img src="https://drive.google.com/uc?id=19lw-X3pYa3NWapNsYEJctiA6mr80Shdp">

### Room Type and Price
From the plots above we can see:

* Entire home/apt has a consistent number of outliers. It means that the price variance on this one is really strong
* The cheapest type of room is the shared room, followed by private rooms and entire rooms.
* The mean price for entire rooms/apts is almost 4 times more expensive than shared rooms, and more than 2 times for private rooms.


<img src="https://drive.google.com/uc?id=1FbFFYkmX_FYfxPTF8hVod9MZUjY43ZHg">

<img src="https://drive.google.com/uc?id=1Z2mzAw4MDqJZqx9vbdntBZGwUX2qF5oI">


### Room Type Counting at Each Neighbourhood Group

From these plots we can say:

* People that stay in Manhattan tend to look for entire home/apt, which can also affect demand and increase prices
* In Brooklyn and Queen, the demands for private rooms and entire rooms are close to each other.
* Shared rooms are the least popular type on the listings.

<img src="https://drive.google.com/uc?id=1uUoKvXSu2Ij1P2STRoMug7woED6RNnUn">


### Room Type Average Price at Each Neighbourhood Group

We can see that:

* Entire room/apt avg price is higher for Manhattan and Brooklyn, respectively.
* In Manhattan and Brooklyn, private rooms are in average more expensive than shared rooms.
* In Queens Private Rooms and Shared Rooms have the almost the same average price

<img src="https://drive.google.com/uc?id=1ww9t2YY0sUR02Yu0kXmT7AZVSyZMW9NE">

### Description and Price Analysis

<img src="https://drive.google.com/uc?id=1CyUs_GQ15s--4A3y5X7NW3p5StgqYu1f">


# Data Engineering

* <a href="https://github.com/dimitriarthur/AIRBNB-Data-Analysis/tree/main/Data%20Engineering%20Artifacts" target="_blank"> Full Data Engineering Here</a>

## Pipeline Description

* MeanImputation: given a list of input columns, it fills the null values of an output column with the average value of the input grouping
* DropRows: given a list on input columns, this stage drops all the rows where there are null values
* logTransform: takes an input column and apply a log transformation
* cleanText: takes an input column and removes all the special characters from the text
* cleanOutliers: takes an input column and a threshold, which determines the dataframe rows that satisfy the condition
<img src="https://drive.google.com/uc?id=1Fl-80kElIgAOS2SB16IARf48zsKzpo25">

### Pipeline Transformations - Quality Assurance 

* <a href="https://github.com/dimitriarthur/AIRBNB-Data-Analysis/tree/main/QA%20Artifacts" target="_blank"> Full Pipeline Transformation Tests</a>


# Machine Learning Experimentation 

* <a href="https://github.com/dimitriarthur/AIRBNB-Data-Analysis/tree/main/ML%20Experimentation" target="_blank"> Full ML Experimentations</a>

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-7btt{border-color:inherit;font-weight:bold;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-7btt"></th>
    <th class="tg-7btt" colspan="2">R^2 Score</th>
    <th class="tg-7btt" colspan="2">RMSE</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow">Without Text Fts</td>
    <td class="tg-c3ow">With Text Features</td>
    <td class="tg-c3ow">Without Text Fts</td>
    <td class="tg-c3ow">With Text Features</td>
  </tr>
  <tr>
    <td class="tg-c3ow">GBT Regressor</td>
    <td class="tg-c3ow">0.554</td>
    <td class="tg-c3ow">0.557</td>
    <td class="tg-c3ow">0.18</td>
    <td class="tg-c3ow">0.18</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Random Forest Regressor</td>
    <td class="tg-c3ow">0.538</td>
    <td class="tg-c3ow">0.547</td>
    <td class="tg-c3ow">0.182</td>
    <td class="tg-c3ow">0.181</td>
  </tr>
</tbody>
</table>
