<div align="center">

![banner](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Title_Image.PNG)

# Final Project - Common Issues & Delays in Air Travel

</div>



## Table of Contents

* [Reasons Why We Selected This Topic](#Reason-Why-We-Selected-This-Topic)<br>
* [Description of Source Data](#Description-of-Source-of-Data)<br>
* [Main Topics We Hope to Address with the Data](#Main-Topics-We-Hope-to-Address-with-the-Data)<br>
* [Description of Communication Protocols](#Description-of-Communication-Protocols)<br>
* [Database](#Database)<br>
* [Dashboard](#Dashboard)<br>
     * [Storyboard](#Storyboard)<br>
     * [Tableau Visualizations](Tableau-Visualizations)<br>
* [Air Travel Overview](#Air-Travel-Overview)<br>
* [Flight Delays and Cancellations](#Flight-Delays-and-Cancellations)<br>
     * [Flight Delay Prediction Model](#Flight-Delay-Prediction-Model)<br>
* [Flight Accidents & Incidents](#Flight-Accidents-&-Incidents)<br>
     * [Accidents Weather Analysis](#Accidents-Weather-Analysis)<br>
          * [Data Cleaning](#Data-Cleaning)<br>
          * [Types of Weather Conditions and Their Association with Aviation Accidents](#Types-of-Weather-Conditions-and-Their-Association-with-Aviation-Accidents)<br>
          * [Frequency of Aviation Accidents with Different Weather Conditions](#Frequency-of-Aviation-Accidents-with-Different-Weather-Conditions)<br>
          * [Aircraft and Weather Conditions](#Aircraft-and-Weather-Conditions)<br>
* [Analysis of Mishandled Baggage](#Analysis-of-Mishandled-Baggage)<br>



## <b>Reason Why We Selected This Topic</b>

For the past century, air travel became the most popular and convenient means of travel for long distances. Nevertheless, it is not uncommon to encounter various problems along the way, including aircraft technical issues and mishandled luggage. Additionally, the most common issue travelers face are delays and cancellations that can be caused by inclement weather or overbooking. 

Despite all of these issues, air travel still remains as the most popular choice for many people, therefore, understanding these issues and the data behind it can be hugely beneficial for future travel.  

<div align="center">

![plane_sunset](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Plane_sunset.jpg)

</div>



## <b>Description of Source of Data</b>

We will explore multiple datasets of flight information and use statistical and machine learning techniques to predict whether an issue may arise while traveling.

The primary source of the data will be exported from raw CSV files by the [Bureau of Transportation](https://transtats.bts.gov/Fields.asp?gnoyr_VQ=FGK), the [Federal Aviation Administration](https://www.asias.faa.gov/apex/f?p=100:1::::::), and the [Department of Homeland Security](https://www.dhs.gov/tsa-claims-data).



## <b>Main Topics We Hope to Address with the Data</b>

With the datasets provided, we hope to create comprehensive analysis and visualizations to:

* Understand air traffic volume and trends over past years
* Explore and compare the most common US airlines and the issues they face
* Create a Machine Learning model that can predict future flight delays and cancellations based off of past data
* Investigate flight accidents in correlation to different airlines, aircraft manufacturers, and airport locations
* Understand the severities of flight accidents based on month, day of the week, and carrier
* Evaluate how the frequency and severity of aviation accidents varies with different weather conditions
* Examine the different causes of flight accidents and incidents, such as environmental issues, human factors, and aircraft performance
* Research how TSA and security lines affect overall air travel experience based on different airports
* Assess mishandled baggage data in comparison to different months and airlines



## <b>Description of Communication Protocols</b>

As the primary source of communication, a Slack group was created. Additionally, we will utilize the allotted time in class meetings to discuss our projects/assignments collaboratively.



## <b>Database</b>

For our project, we decided to use PGAdmin SQL as our database. PGAdmin SQL is a powerful and scalable database management database system which means it can handle large amounts of data and high volumes of transactions. It is also compatible with a wide range of tools and technologies making it easy to integrate with other systems and applications which will be useful when connecting to our Machine Learning Model.

A screenshot can be seen below using the <b>join method</b> on PGAdmin SQL.

![SQL_Table_Schema](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/SQL_Tables_Schema.PNG)


![SQL_join](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/SQL_join.PNG)

The <b>Entity Relationship Diagram (ERD)</b> can be found below.

![ERD](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Connections_Quickdbd.PNG)

A connection string has been built between our Machine Learning dataset [here](https://github.com/billywkim/Final_Project/blob/main/Delays_ML/Delays_ML.ipynb) and the PG Admin database.

![ML_Connection](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Machine_Learning_Connection.PNG)



## <b>Dashboard</b>

Dashboards and storyboards are important for data analysis because they provide a way for users to quickly and easily understand complex data sets so they can help users make better decisions by providing them with a clear and concise view of the data.



### <b>Storyboard</b>

An initial draft of our Storyboard created on Google Slides can be found [here](https://docs.google.com/presentation/d/16ui3_aKnWDj3g7POys37TOuYBOLekHT9SUnBKHB52M0/edit#slide=id.gcb9a0b074_1_0). 



### <b>Tableau Visualizations</b>

The main elements and visualizations on the Storyboard were created using Tableau Public. All of the visualizations on Tableau Public can be viewed [here](https://public.tableau.com/app/profile/william.kim4690/viz/WeatherDelaysbyAirline_16734964116180/Story1?publish=yes). All of these vizualizations are interactable by filtering them through desired airlines, aircraft manufacturers, years, and injury severity.



## <b>Air Travel Overview</b>

Air travel has seen significant growth, with the number of passengers increasing steadily in the recent years. In the US there is a vast network of airports and airlines, with the largest airlines being American Airlines, Delta Air Lines, and United Airlines. The high season for air travel is during the summer, with July having the highest number of travelers, 81 million passengers on average. The low season is during the winter, with February averaging at 61.5 million passengers. Airfare prices tend to be higher during the summer high season and lower during the winter low season. 

<div align="center">

![Number of Air Travel Passengers in US](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Number%20of%20Air%20Travel%20Passengers%20in%20US.png)

</div>



## <b>Flight Delays and Cancellations</b>

In 2022 in the US there was a total of 5,625,620 flights operated. Out of these flights 4,335,485 arrived on time and 1,132,113 were delayed. This means that an enormous 20.12% of all flights were delayed. Additionally, 144,515 flights were cancelled, which is about 2.57% of all flights.

Recent data from the US Bureau of Transportation Statistics for 2021 shows that air carrier delay is the primary cause, accounting for 40% of all flight delays. This means that issues such as overbooking, crew scheduling, and other operational issues within the airline are the primary reason for delays. Another significant cause of delays, accounting for 35% is categorized as aircraft arrives late. This includes situations where a holdup of a previous flight with the same aircraft causes delay for subsequent flight. Additionally, 17% of all delays were caused by National Airspace System (NAS) issues, which include problems with air traffic control systems and air traffic congestion. Extreme weather, such as strong winds, thunderstorms, and other severe weather conditions, is another notable source of flight delays, accounting for 7% of all delays. Interestingly, security delay, which includes issues with airport security and TSA procedures, is the least major cause of all flight delays, accounting for less than 1%. 

![Flight Delays](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Delay.PNG)


### <b>Flight Delay Prediction Model</b>

For our analysis, we decided to use Supervised Machine Learning in order to predict whether a flight would arrive with a delay of 15 minutes or more. Supervised Machine Learning is a type of machine learning where the model is trained on labeled data. In the context of predicting airline delays, this means that the model is trained on a dataset that includes information about past flights, such as departure and arrival times, airline, and whether or not the flight was delayed. The goal of the model is to learn from this labeled data and make predictions about whether future flights will be delayed.

Before implementing a machine learning model, we performed a number of steps to prepare the data for analysis. This process, known as data preprocessing, involved cleaning and transforming the raw data to make it more suitable for modeling. In our case we have decided to drop any rows with null values as well as any columns where all values are null.

In order to successfully run our machine learning model, a wide range of preliminary features were selected, such as: 

* Day of the week/Day of the month: Certain days may be more prone to delays due to factors such as holidays, weather patterns, or air traffic volume

* Airline/Flight Number: This can help identify specific flights or airlines that are more subjective to delays

* Flight origin and destination: Delays at certain airports may be more common due to factors such as congestion or maintenance issues

* Departure time: Flights that depart during peak travel times or in adverse weather conditions may be more prone to delays

Once the data was in a suitable format, we split it into a training set and a testing set. The training set was used to build the model, while the testing set was used to evaluate its performance. This separation is important because it allows us to test the model's ability to adapt to new, unseen data.

To achieve our goal, we decided to test several different approaches to train and evaluate data models. We started with Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifier. We then oversampled the data using the RandomOverSampler and SMOTE algorithms, and then under sampled the data using the ClusterCentroids algorithm. Afterwards, a combinatorial approach of over- and under sampling using the SMOTEENN algorithm was deployed.

After comparing all of the models, Balanced Random Forest Classifier performed the best with a balanced accuracy score of 91.5%. The main benefit of this model is its ability to achieve a high level of accuracy, which means that it is able to make correct predictions for a large proportion of the samples in the dataset. Additionally, a Balanced Random Forest Classifier is designed to handle imbalanced datasets, which means that it can perform well even when there is a disproportionate number of samples in one class compared to the other. It is important to note that this model also has its limitations such as overfitting, which means the model might perform well on the training data but poorly on new, unseen data.

This approach allows us to automate the process of predicting delays and to potentially improve upon it over time as new data becomes available.

Please see [Delays_ML](https://github.com/billywkim/Final_Project/blob/main/Delays_ML/Delays_ML.ipynb) for our current Machine Learning progress.

<div align="center">

![multiple_planes](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Multiple_planes.jpg)

</div>



## Flight Accidents & Incidents



### <b>Accidents Weather Analysis</b>

Aviation accidents in relation to weather is a significant concern for the aviation industry. Weather conditions such as thunderstorms, icing, and turbulence can greatly affect the safety of flights and increase the risk of accidents. In this section, we will explore the types of weather conditions most commonly associated with aviation accidents, the frequency of aviation accidents with different weather conditions, whether certain types of aircraft are more prone to accidents in certain weather conditions, the severity of aviation accidents with different weather conditions, geographical regions that are more prone to aviation accidents due to weather conditions, and specific precautions that can be taken to prevent or mitigate aviation accidents in certain weather conditions.

The dataset for the analysis can be found [here](https://github.com/billywkim/Final_Project/blob/main/Resources/AviationData_Weather.csv)

![image](https://user-images.githubusercontent.com/110706169/212215561-207c0b20-a926-49e9-b7de-bfe5a69e55f1.png)

#### Data Cleaning

* Check % missing data and drop columns >35% missing
* Filter the dataset where:
	- Aircraft_Category = Airplane
	- Country = United States
	- Investigation_Type = Accident
* Change date 'objects' to 'datetime'
* Change latitude and longitude from strings to float
* Split Location into City and State
* Bucket Airport_Names with same labels
* Bucket Airport_Code with same labels
* Add 'Season' column
* Bucket Registration_Numbers with same labels
* Change 'Make' column to 0s and 1s instead of Y/N
* Merged Injury_Severity labels

#### Types of Weather Conditions and Their Association with Aviation Accidents
![image](https://user-images.githubusercontent.com/110706169/212218308-67ef79ae-ac37-4f17-8f0f-b2c8b9667aa6.png)![image](https://user-images.githubusercontent.com/110706169/212218278-6234d2f1-d7f7-4b2b-b099-9de89e523372.png)

In the United States, the seasons are generally defined as spring (March-May), summer (June-August), fall (September-November), and winter (December-February). The specific weather conditions can vary greatly depending on the region of the country, but here is a general overview of what you might expect during each season:

Spring: As the weather begins to warm up, many areas of the country will see increasing rainfall and thunderstorms. The northern regions may still see some snow and cold temperatures, while the southern regions will start to experience warmer weather.

Summer: This is typically the warmest time of year in the US, with high temperatures and humidity in many regions. The southern and central regions of the country are particularly known for their hot and humid summers. Thunderstorms and hurricanes are also more common during this time in some areas.

Fall: As the weather starts to cool down, many regions will experience changing foliage and mild temperatures. Rainfall and thunderstorms can still be common, but the weather is generally more stable than during spring.

Winter: This is typically the coldest time of year in the US, with snow and ice storms in many northern regions, and freezing temperatures in many other areas of the country. Some southern regions may see milder temperatures, but heavy rainfall can still be a possibility.

#### Frequency of Aviation Accidents with Different Weather Conditions
![image](https://user-images.githubusercontent.com/110706169/212218442-93e866dd-3371-490a-8c0c-bc3859eed472.png)

#### Aircraft and Weather Conditions
![image](https://user-images.githubusercontent.com/110706169/212218520-241b66c6-bb73-4834-905a-c6488739b888.png)



## <b>Analysis of Mishandled Baggage</b>

Mishandled baggage is one of the common issue faced by travelers all around the world. When baggage is not handled properly, it can lead to inconvenience and frustration for the traveler, who may be left without essential items or personal belongings for an extended period of time. Using data from the Bureau of Transportation for 2019, 2020, and 2021, an analysis was created to discover the following key points: 
* In 2019, 0.6% of all checked baggage was mishandled. This percentage decreased in 2020 to 0.42%  most likely due to the global pandemic and general decrease in travel. In 2021 there was a significant increase, with approximately 0.5% of checked baggage being mishandled.
* According to the analysis, the percentage of mishandled baggage varied throughout the year, with the highest percentage occurring in June at 0.63% and the lowest percentage occurring in September at 0.43%. Higher mishandled baggage percentages can be observed during the summer and winter but lower during the spring and fall seasons.
* The percentage of mishandled baggage also fluctuates based on the airline. Allegiant Air had the lowest percentage of mishandled baggage at 0.16%, while Envoy Air had the highest percentage at 0.86%. 
* Interestingly, Southwest Airlines had one of the highest number of enplaned baggage while maintaining one of the lowest mishandled baggage percentage at 0.37%. American Airlines has similar enplaned baggage amounts to Southwest Airlines but has the second highest mishandled baggage rate at 0.76%.

<div align="center">

![bag_delay](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/baggage_delay.jpg)

</div>