<div align="center">

# Final Project - Common Issues & Delays in Air Travel

![banner](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/Title_Image.PNG)

</div>



## <b>Reason why we selected this topic</b>


For the past century, air travel became the most popular and convenient means of travel for long distances. Nevertheless, it is not uncommon to encounter various problems along the way, including aircraft technical issues and mishandled luggage. Additionally, the most common issue travelers face are delays and cancellations that can be caused by inclement weather or overbooking. 

Despite all of these issues, air travel still remains as the most popular choice for many people, therefore, understanding these issues and the data behind it can be hugely beneficial for future travel.  



## <b>Description of Source of Data</b>

We will explore multiple datasets of flight information and use statistical and machine learning techniques to predict whether an issue may arise while traveling.

The primary source of the data will be exported from raw CSV files by the [Bureau of Transportation](https://transtats.bts.gov/Fields.asp?gnoyr_VQ=FGK), the [Federal Aviation Administration](https://www.asias.faa.gov/apex/f?p=100:1::::::), and [Department of Homeland Security](https://www.dhs.gov/tsa-claims-data).



## <b>Main Topics We Hope to Address with the Data</b>

With the datasets provided, we hope to create comprehensive analysis and visualizations for:

* Overall analysis and comparison of the most common issues among airlines in the US
* Probability of flight interruptions and problems
* Correlation of flight accidents with time of day, cities, etc... 
* Flight issues related to inclement weather 
* Mishandled baggage



## <b>Description of Communication Protocols</b>

As the primary source of communication, a Slack group was created. Additionally, we will utilize the allotted time in class meetings to discuss our projects/assignments collaboratively.



## <b>Flight Delay Prediction Model</b>

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



## <b>Database</b>

For our project, we decided to use PGAdmin SQL as our database. PGAdmin SQL is a powerful and scalable database management database system which means it can handle large amounts of data and high volumes of transactions. It is also compatible with a wide range of tools and technologies making it easy to integrate with other systems and applications which will be useful when connecting to our Machine Learning Model.

![SQL_Table_Schema](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/SQL_Tables_Schema.PNG)


![SQL_Table_Output](https://github.com/billywkim/Final_Project/blob/main/Resources/Screenshots/SQL_Table_Output.PNG)



## <b>Analysis of Mishandled Baggage</b>

Mishandled baggage is one of the common issue faced by travelers all around the world. When baggage is not handled properly, it can lead to inconvenience and frustration for the traveler, who may be left without essential items or personal belongings for an extended period of time. Using data from the Bureau of Transportation for 2019, 2020, and 2021, an analysis was created to discover the following key points: 
* In 2019, 0.6% of all checked baggage was mishandled. This percentage decreased in 2020 to 0.42%  most likely due to the global pandemic and general decrease in travel. In 2021 there was a significant increase, with approximately 0.5% of checked baggage being mishandled.
* According to the analysis, the percentage of mishandled baggage varied throughout the year, with the highest percentage occurring in June at 0.63% and the lowest percentage occurring in September at 0.43%. Higher mishandled baggage percentages can be observed during the summer and winter but lower during the spring and fall seasons.
* The percentage of mishandled baggage also fluctuates based on the airline. Allegiant Air had the lowest percentage of mishandled baggage at 0.16%, while Envoy Air had the highest percentage at 0.86%. 
* Interestingly, Southwest Airlines had one of the highest number of enplaned baggage while maintaining one of the lowest mishandled baggage percentage at 0.37%. American Airlines has similar enplaned baggage amounts to Southwest Airlines but has the second highest mishandled baggage rate at 0.76%.
