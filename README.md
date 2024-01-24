## Project Description:
The main goal of this project is to predict whether the Falcon 9 first stage will land successfully. SpaceX prides itself in being able to reuse the first stage of a rocket launch so much so that they advertise on their website that their rocket launches cost 62 million while other providers cost upward 165 million. Much of these savings are down to the first stage's reusability. If we can determine if the first stage will land, we can determine the cost of a launch. This information can be used if an alternate company wants to bid against SpaceX for a rocket launch.

This brings us to our main question that we are trying to answer: **For a given set of features about a Falcon 9 rocket launch, will the first stage of the rocket land successfully?**

The methodolgy followed will include Data Dollection, Data Wrangling and Preprocessing, Exploratory Data Analysis, Data Visualization and finally, Machine Learning Prediction.

During our investigation, the results of our analysis indicate that there are some features of rocket launches that have a correlation with the success or failure launches.

In the end we conclude that the Decision Tree may be the best machine learning algorithm for this problem.

For the full project report you can check out the PDF in this repository.

### Table Of Contents:
The project includes seven Jupyter Notebooks, one Powerpoint Presentation and one PDF :
- Space-X Data Collection with API

- Data wrangling

- EDA with SQL

- EDA with Data Visualisation

- Interactive Map Analytics with Folium

- Space-X Dashboard

- Space-X Machine Learning Prediction

## 1. Space-X Data Collection API
The API used is [here](https://api.spacexdata.com/v4/launches/past)

The API provides data about types of rocket launches done by SpaceX
The data is cleaned and exported to CSV for analysis
[the wikipedia page](https://en.wikipedia.org/wiki/List_of_Falcon_9_and_Falcon_Heavy_launches)

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/labs/module_1_L2/images/falcon9-launches-wiki.png)

## 2. Data Wrangling
We perform some Exploratory Data Analysis (EDA) to find some patterns in the data and determine what would be the label for training supervised models.

In the data set, there are several different cases where the booster did not land successfully. Sometimes a landing was attempted but failed due to an accident;
for example, <code>True Ocean</code> means the mission outcome was successfully  landed to a specific region of the ocean while 
<code>False Ocean</code> means the mission outcome was unsuccessfully landed to a specific region of the ocean. 
<code>True RTLS</code> means the mission outcome was successfully  landed to a ground pad <code>False RTLS</code> means the mission outcome was unsuccessfully landed to a ground pad.
<code>True ASDS</code> means the mission outcome was successfully landed on  a drone ship <code>False ASDS</code> means the mission outcome was unsuccessfully landed on a drone ship.

Successful landing example:

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0701EN-SkillsNetwork/api/Images/landing_1.gif)


## 4. Exploratory Data Analysis with SQL
We use SQL to query the database and answer several questions about the data such as:

 * The names of the unique launch sites in the space mission
 * The total payload mass carried by boosters launched by NASA (CRS)
 * The average payload mass carried by booster version F9 v1.1
Some of the SQL statements or functions used include SELECT, DISTINCT, AS, FROM, WHERE, LIMIT, LIKE, SUM(), AVG(), MIN(), BETWEEN, COUNT(), and YEAR().

## 5. Exploratory Data Analysis with Data Visualization
We use Python's Matplotlib and Seaborn libraries to visualize the relationships that exist within the dataset.
The "One-Hot Encoding" technique is used to create binary category variables as part of the Feature Engineering
Visualizing the success rate in each orbit:

Class 1 = Success
Class 0 = Failure
![](./img/LaunchSite_vs_flightnum.PNG)

## 6. Interactive Map Analytics with Folium
In this notebook we perform the following:

* Mark all launch sites on a map
* Mark the success/failed launches for each site on the map
* Calculate the distances between a launch site to its proximities
This is all done using Folium, a Python mapping library that allows for the creation of interactive maps.

Launch sites:

![](./img/launchsite.PNG)
Launch site proximities distances such as railway line, main road and coast:

## 7. Space-X Dashboard

To access the dashboard, this notebook must be cloned and run on your local machine.

Installation requirements:
- Python 
- pandas
- dash
- plotly

Execute all the cells. The final cell will output a statement saying "Dash is running on server. Click on the link and the dashboard will open up in your browser.  

![](./img/dash.PNG)

## 8. Space-X Machine Learning Prediction

In this notebook we perform the following:

- Create a column for the `Class`
- Standardize the data
- Split into training data and test data
- Find best Hyperparameter for SVM, Classification Trees and Logistic Regression
- Find the method that performs best using test data

## Conclusion:

- The analysis showed that there is a positive correlation between number of flights and success rate as the success rate has improved over the years. 
- There are certain orbits like SSO, HEO, GEO, and ES-L1 where launches were the most successful.
- Success rate can be linked to payload mass as the lighter payloads generally proved to be more successful than the heavier payloads. 
- The launch sites are strategically located near highways and railways for transportationof personel and cargo, but also far away from cities for safety.
- The best predictive model to use for this dataset is the Decision Tree Classifier as it had the highest accuracy.