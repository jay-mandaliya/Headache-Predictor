# Headache-Predictor

### Project Scenario
-----
The porject scenario showcase the event when a student has moved to a new location in Halifax city and has been suffering from a headache. After consulting the doctor, the student realized that the reason for the headache is due to the Halifax weather, the workout schedule and working long hours. Due to this reason, the doctor asked the student to make a journal and note down the details regarding the headache duration, workout time and the work schedule.

### Weather Data
-----
It was decided to move forward with the datasets from two weather stations. The first station is identified as “HALIFAX DOCKYARD” and the second station is identified as “HALIFAX KOOTENAY”. Our collected weather data is recorded on an hourly basis and on the weather normal for the recorded day.

### Data Pre-processing
-----
For developing models, it was required error-less data which was available from the weather source and the journal data. The journal data was clean and important, so nothing is to be done with the journal data pre-processing. While considering the weather data, it was found that some of the columns had a majority of null values, while some columns had duplicate and repeating values. Hence, it was calculated by mean and standard deviation, the weather dataset was pre-processed and columns were removed which contain empty or null values and have discarded the values which were repeating. Also, Data sets from the website are separate by month when it was joined. Note that for testing data sets 3 days were assumed as work out days in 2020.

### Feature Selection
-----
At the first glance , the most important features were Temperature, Dew Point, Relative Humidity, Wind Direction, Wind Speed and Atmospheric Pressure from the weather dataset. Features were sustained for the data modelling to find out which of the features mentioned above relates with the headache of the student. Also, the work hours were added in this scenario which at any hour the amount of time that student works till then in that day is added, and for any hour that student has physical training we put it as 1 as true.

#### Question 1 — What is the most important factor for his headache? Why?
-----
![alt text](/images/1.png)  
Very detailed analysis were performed on the data, and made a heatmap of the data. First, the correlation between data was found. It is important to avoid any highly correlated data since they can be harmful for the training model. As we can see dew and temperature are highly correlated, dew temperature was deleted. Also, weekday and work-hour and working day are highly correlated, so only work-hour was considered. This is because if we have high correlated data in our dataset then data set will be inaccurate and unbiased for the training model. After that the class weight were found for the severity and the time of the headache.

Now the accuracy per decision for the unbalance and balance dataset was checked. It is shown in the figure below.
![alt text](/images/2.png)

#### Question 2 — When will he get a headache between (Sep 1, 2020 – Dec 30, 2020) and what is the probability of his headache.
-----
The trained model is now used to predict the headache
![alt text](/images/3.png)

#### Question 3 — For days that the probability of headache is more than 70%, suggest a significant action to decrease the headache's probability.
-----
So because our model insists that since the working day is a usual activity and the headache day can not be related to the day of the work and also as we can see we do not have any information for the workout day in 2020 we can not say if it is important or not in our testing. We should recommend the student to avoid and protect themselves from the weather by any action by chosing right type of dressing. So as the most factors in our model is humidity, temperature, and wind speed this should be taken care. Also data related to headache are less and can cause a problem to find any relation to avoid the possibility of headache. In the graph below we can see the accuracy of decision based on the factors and depth tree. So the data is not enough to decide whether the working and work out helping or avoiding headache or not. The model needs more data to be accurate.
![alt text](/images/4.png)
