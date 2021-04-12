# Citi Bike System Data Eploration and Analysis
## by Nour Emam


## Dataset

The dataset was obtained via Bikeshare. It consists of just over 4 million records and 11 variables. Each record represents one trip and the data is monthly for the years 2019 and 2020. The variables that describe a trip include trip duration, start and end station, start and end date as well as some user specific data such as age, user type (can be a customer or a subscriber) and gender. The files downloaded for 2019 and 2020 data can be found [here](https://s3.amazonaws.com/tripdata/index.html). The code to download the files programatically and prepare the CSV files can be found in the exploration notebook since the files were too large to attach.

### Data Wrangling
In order to build the 2019 and 2020 csv files used in the analysis (also included in the project submission folder). Requests library was used to download the data programatically and extract the data from the zipped files. Please note that due to the huge number of records per month, a random sample was generated from each month for the 2019 and 2020 datasets to accomodate the limited processing power available to run this analysis. The dataset was also enriched with derived columns such as age range, month and duration in minutes.


## Summary of Findings

In the exploratory analysis, the distribution of the different variables indicated the population among which Citi Bike is most popular. Age distribution showed that most users are between the age 25-29, 65% of the dataset have the gender 'Male' and 81.47% of the users are subscribers with annual passes to use the bike rental platform. As for the duration, it was originally given in seconds and the initial distribution plot showed that it is spread out across a vast range of values with huge differences. I tried plotting the data on a log scale but the best graph was obtained when using the duration in minutes which was also more interpretable. This graph showed the peak between 5 and 10 minutes and the graph was righ skewed with a long tail to the right. It is also worth mentioning that 40,048 out of 4,005,853 rows (just under 1% of the dataset) show trip duration of more than 1.25 hours which is more than the 99th percentile of the data points. Those records were removed as they would cause skewness and inconsistencies in the data. Average trip duration against age range showed that users aged 50-54 had the highest average duration. 

Also, it was observed that male users tend to rent the bikes for shorter durations than female renters even though the users with the gender 'unknown' had the highest mean duration of around 20 minutes. As for user types, the data showed that subscribers go for shorter trips while customers on the other hand tend to ride the bikes for longer durations. It was also observed that June was the month with the highest trip duration. 

Among some of the other interesting relationships found was that most customers have 'unknown' as the gender and most users aged 50-54 are customers. Also looked at the impact of COVID-19 on the platform, number of trips began to decline in March and there was a sharp fall in April. However, an interesting observation is that by September number of trips taken in 2020 were higher than previous year and this trend carried on for the rest of the year. Interestingly, average duration of trips in 2020 was actually higher than 2019. A closer look at the relationship between age range and user type showed that older customers tend to enjoy longer trips with the bikes. Finally, it was observed that most users aged 50-54 have an unknown gender which showed that group having the highest average trip duration when comparing age range and gender. This is followed by Females aged 16-24. Same graph for 2020 showed higher trip durations as confirmed before by a graph comparing duration over month and year.

## Key Insights for Presentation

In the presentation, I focused on the distribution of the data to show the different characteristics of Citi Bank users. I also focused on examining the relationship between month and user type, age range and user type and age range and gender. Finally I highlighted the effects of COVID-19 on number of trips and their duration.