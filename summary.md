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

















## Predicting the probability of COVID-19 positive

For this question, We want to use Temperature, Oxygen and Pulse Rate readings to predict the probability of a person who had COVID-19 positive. The data set contains 10,000 observations after removing NA, and we select some useful variables to predict.It should be noted that, result is binary categorical variable,so we choose Logistic Regression Model.Then we get the probability of COVID-19 positive = 

exp(32.4 + (-1.15) * Oxygen + 0.0145 * Pulse Rate + 0.729 * Temperature)
____________________________________________________________

(1+exp(32.4 + (-1.15) * Oxygen +  0.0145	* Pulse Rate + 0.729 * Temperature))

and the probability of COVID-19 positive is proportional to temperature and Pulse Rate and inversely proportional to Oxygen.(The reason why it's inversely proportional to Oxygen is because the Oxygen can keep blood in a high-energy state,through the lungs into the capillaries, has a certain role in human metabolism.)Below there are the meanings of slope and intercept:
Slope - Oxygen: All else held constant, for every one percent increase in Oxygen, we would expect the probability of COVID-19 positive to be lower, on average, by 1.15 percent.

Slope - Pulse Rate: All else held constant,the Pulse Rate increases by one beat per minute, we would expect the probability of COVID-19 positive to be higher, on average, by 0.01447323 percent.

Slope - Temperature: All else held constant, for every one degree Fahrenheit increase in Temperature, we would expect the probability of COVID-19 positive to be higher, on average, by 0.72863310 percent.

Intercept: Doesn't make sense in context.

Then we make predictions for test data,plot the ROC curves,and calculate the areas under the ROC curves,and we find model performs better, because it has o.98 areas under the line,is close to 1.


