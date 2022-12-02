COVID-19
===========

# Summary

## ORIGIN OF COVID-19
Three years ago, a new kind of pneumonia named COVID-19 appeared in Wuhan, the capital of China's Hubei province, and began to spread in the world. People who caught COVID-19 always have a high temperature or shivering and a continuous cough.Transmission rate appeared to escalate in mid-Tanuary 2020. As of 30 January 2020, approximately 8,243 cases have been confirmed. People who got COVID always have a fever and bad cough. Also,there are obvious changes in patients' vital signs.

To find more information of COVID-19, we got two dataset from the Kaggle website. COVID-19 DATASET contains the number of confirmed, death, recovered and active people from January to the end of July in 2020 in different region. Covid-19 Temperature, Oxygen & Pulse Rate readings contains three vital signs of 10000 patients.

## World overview
Firstly , we made two line graphs of confirmed cases and deaths over time, with colors representing different World Health Organization (WHO) regions of the world, such as Europe and Asia. These graphs give us a comprehensive understanding of the epidemic and let us find the direction of exploration.

1.Confirmed case

According to the graph “Number Of COVID-19 Cases Over Time”, in first three months of 2020, COVID-19 did not seen as a serious disease, and majority of patients came from Asia. After February 12, the growth rate in Asia slowed down and the rate of increase leveled off. In April, Americas region has recorded plenty of patients and became the hardest-hit area---the cumulative number of confirmed cases surpassed that of Asia, of which the United States is the country with the largest number of confirmed cases in the world. Meanwhile,the epidemic situation in Europe worsened, and the number of confirmed cases increased rapidly. In July, there has been 16480485 confirmed in the world, however, Americas region took up more than a half. The increasing of the confirmed cases in other region has been flat.

2.Deaths

The overall development trend of global cumulative death cases can be divided into three stages
(1) From January 20 to March 8, the slow growth period: the main feature of this period is that the number of new deaths in a single day does not exceed 100, and the cumulative number of deaths worldwide is dominated by Asia (mainly China).
(2) From March 9th to March 24th, the rapid growth period: the main feature of this period is that the number of new deaths in a single day is greater than 200 but not more than 2,000. The death rate in Europe has increased significantly. The global death cases are mainly distributed in various regions dominated by Europe and Asia.
(3) April 15-August, continuous outbreak period: The main feature of this period is that the number of new deaths in a single day exceeds 5,000, and the current number of new deaths in a single day is as high as 15,000. The number of deaths in the Americas (mainly the United States) continued to rise at an alarming rate - surpassing Europe as the region with the highest number of deaths in a month.

Then we plotted two graphs of the top 15 countries with the number of confirmed cases and deaths and found that Americas region is the hardest-hit area in both deaths and confirmed number as expected. So in the following details, we would pay more attention to Americas region,especially USA. We will also use death and recovered variables to do some data visualization.

## Recovery rate of COVID-19 in different countries
We have retrieved the number of new crown infections and the number of recovered people in various countries in the world in 2022, and the recovery rate of the new crown virus can be obtained from our obtained data. In the figure, we can see that the recovery rates of different countries are not the same or even very different. Next, we will analyse the recovery rate in different regions. Then we extracted the data of countries with low recovery rate and countries with high recovery rate, and made a bar picture to clearly show that the recovery rate of the lowest country is even less than 10%, while that of countries with high recovery rate is even more than 98%, which is a very large range. Before data collation, it was speculated whether the recovery rate was related to the country's economic and welfare policies. However, after obtaining different recovery rates and using Internet search engines, the data was not the same. Among countries with higher recovery rates, the per capital GDP of regions with higher recovery rates even reached 51875 dollars per person, while that of regions with lower GDP was only 787 dollars. Countries with low recovery rates have the same situation. It can be seen that recovery rates are not closely related to the national economy. In the process of data selection, we can clearly see that more countries have higher recovery rates from the data of all countries. Therefore, we can get that COVID-19 is not 100% fatal, and if it is unfortunately infected, there will be a greater chance of recovery, of course, it also depends on your region. In the process of analysing this problem, it is a very intuitive way to use r language to analyse and make icons.

## the map of Covid distribute 
In this question, we want to use maps to introduce the distribute of covid-19 in the year of 2020. Then we use ggplot2 generate two maps of covid-19 distribution, which are worldwide distribution and USA distribution separately due to the reason that from the data USA was the country hold the largest confirmed value in the year of 2020.

1.worldwide

In this part, we use function map_data to give latitude and longitude to the countries over world. Then we left join the formed chart to the original chart by region, so the original chart can have latitudes and longitudes within it. After that we just choose countries who have confirmed data to form a map reflecting the number of confirmed cases in different countries depending on the color of the map. In the end we eliminate the figure of latitude and longitude along the x, y axis to make it simpler. In this case, area that does not have much confirmed number is represented by green and the other situation is represented by red. From the map we got, we can find that south America and Southern Asia have the largest affected value. What’s more, the population in these areas happen to be very high compared with other continents.

2.America

In this part we form a map of covid distribution of America using the same function. What we find in this map is that there are four main area affected by the covid most. These states are California, Texas, Florida, and New York, the top four populous states in America.

So, the situation in America appeared the same trend with the world, more populous area means more confirmed cases. That tells us if we meet another epidemic disease next time, it is better move to area less populous during epidemic periods.

## Predicting the probability of positive results
For this question, We want to use Temperature, Oxygen and Pulse Rate readings to predict the probability of a person who had COVID-19 positive. The data set contains 10,000 observations after removing NA, and we select some useful variables to predict.It should be noted that, result is binary categorical variable,so we choose Logistic Regression Model，then we get the probability of positive = 

exp(32.4 + (-1.15) * Oxygen + 0.0145 * Pulse Rate + 0.729 * Temperature)
____________________________________________________________

(1+exp(32.4 + (-1.15) * Oxygen +  0.0145	* Pulse Rate + 0.729 * Temperature))

The probability of positive is proportional to temperature and Pulse Rate，and it is inversely proportional to Oxygen.(The reason why it's inversely proportional to Oxygen is because the Oxygen can keep blood in a high-energy state,through the lungs into the capillaries, has a certain role in human metabolism.)Below there are the meanings of slope and intercept:
Slope - Oxygen: All else held constant, for every one percent increase in Oxygen, we would expect the probability of positive to be lower, on average, by 1.15 percent.

Slope - Pulse Rate: All else held constant,the Pulse Rate increases by one beat per minute, we would expect the probability of positive to be higher, on average, by 0.0145 percent.

Slope - Temperature: All else held constant, for every one degree Fahrenheit increase in Temperature, we would expect the probability of positive to be higher, on average, by 0.729 percent.

Intercept: Doesn't make sense in context.

Then we make predictions for test data,plot the ROC curves,and calculate the areas under the ROC curves, we find model performs well, because it has o.98 areas under the line,is close to 1.

## DATA
All of the data we use are found on Kaggle.

https://www.kaggle.com/datasets/imdevskp/corona-virus-report?search=COVID-19+DATASET
https://www.kaggle.com/datasets/rishanmascarenhas/covid19-temperatureoxygenpulse-rate
