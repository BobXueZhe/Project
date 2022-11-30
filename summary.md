COVID-19
===========

# Summary

## ORIGIN OF COVID-19

Three years ago, a new kind of pneumonia named COVID-19 appeared in Wuhan, the capital of China's Hubei province, and began to spread in the world. People who caught COVID-19 always have a high temperature or shivering and a continuous cough.

To find the origin of COVID-19, we got the dataset from the Kaggle website. It contains the number of confirmed, death, recovered and active people from January to the end of July in 2020 in different region.

## GLIMPSE OF DATA

To begin with, we made a line plot of confirmed number in 2020 and use color to represent different region in the world, like Europe and Asia. This plot showed us a totally glimpse of the epidemic situation, so that we could find our direction of exploration. In first three months of 2020, COVID-19 did not seen as a serious disease, and majority of patients came from China. So it has not turn to a worldwide illness.

In April, Americas region has recorded plenty of patients and became the hardest-hit area. Meanwhile, the number of patients in all the regions began to increase quickly.So far COVID-19 has become a big problem of the world.

In July, there has been 16480485 confirmed in the world, however, Americas region took up more than a half. 

So in the following details, we would pay more attention to Americas region,especially USA. We will also use death and recovered variables to do some data visualization.

















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


