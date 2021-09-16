# WTWY Gala NYC Subway Outreach Team Arrangement Planning
Chien Yuan Chang

## Abstract
The goal of this project is to identify the busiest entrances and hours among MTA stations in New York with the highest entires and exits between March and May in 2021 for the client, WomenTechWomenYes (WTWY), to place street teams at entrances to promote their gala at the beginning of the summer. I worked with public [MTA turnstile data](http://web.mta.info/developers/turnstile.html), refined the data, conducted exploratory data analysis, and plotted charts. I identified the busiest control areas and times and made a function to help with scheduling by inputting the outreach duration, the amount of teams, and the weekly outreach capacity per team for WTWY.
    
## Design
This project was initiated from the email from WTWY to address their needs to place street teams at entrances to subway stations to outreach to individuals passionate about increasing the participation of women in technology to fill their event space at the beginning of the summer, and also to concurrently build awareness and reach efficiently. The [MTA turnstile data](http://web.mta.info/developers/turnstile.html) is public on MTA website with the data of the entry/exit register values for one turnstile at control area at certain time and date. The data between March and May in 2021 was ingested into local database, and Exploratory Data Analysis (EDA) would enable us to identify the busiest control areas by hours and days of the week among MTA stations in New York with the highest sum of entires and exits between March and May in 2021 and provide WTWY a schedule to put their teams at which control areas on which days at what times.

## Data
The dataset between 3/1/2021 and 5/31/2021 contains 2,747,757 rows with 11 features for each, 6 of which are about the location of the turnstiles, 2 of which are about the date and time, and 2 of which are the entry and the exit register values for one turnstile. 9 of 11 features were used for EDA. We didn't do the analysis on division level which area was too large. Every control area had a unique control area number with only one remote unit number so the features of remote unit numbers and divisions were not selected. The features of station names and linenames were combined into a new feature to present the stations without same station names at different locations. The 


## Algorithms

*Feature Engineering*

1. Including data only between 3/1/2021 and 5/31/2021
2. Removing duplicate data between regular and recover audit to have just one data for a turnstile at a time
3. Combining and converting date and time features into time series data
4. Calculating the difference of the entry and the exit register values from previous register values which were mostly audited every 4 hours to get the features of the numbers of entires and exits at the periods
5. Removing the outliers by the features of the numbers of entires and exits at the periods to reduce the effect from incorrect data entires
6. Summing the the numbers of entires and exits at the periods to get the feature of the sum of entires and exits at the periods
7. Combining the features of station names and linenames into a new feature to present the stations to distinguish different stations shared the same stations names
8. Interpreting time series to the features of time periods (Late Night, Early Morning, Morning, Afternoon, Evening, Night), day of the week and weekday/weekend.


*Exploratory Data Analysis of Daily and Station Level*

1. Grouping by turnstiles and dates to get the sum of entires and exits for each turnstile on each date
2. Summing the sum of entires and exits of every turnstiles in each stations to get the sum of entires and exits for each station on each date
3. Averaging the sum of entires and exits for each station on each date by stations to find **the busiest stations with highest daily average sum of entries and exits** ([Top 10 Busiest Subway Stations](images/top10_avg_daily_visit_staition.png))
4. Summing the sum of entires and exits for each station on each date by dates to get the daily numbers of entires and exits on each date to find **the trend by time** ([Daily Visits of Subway From March to May, 2021](images/total_visit_by_date.png))
5. Averaging the sum of entires and exits on each date by the 7 days of the week to get the average sum of entries and exits for each day of the week to see **the busiest days of the week** ([Average Sum of Entries and Exits by Day of the Week](images/avg_daily_visit_day.png))

*Exploratory Data Analysis of Time Period and Control Area Level* 

1. Grouping by turnstiles, time periods and dates to get the sum of entires and exits for each turnstile within each time period on each date
2. Summing the above sum of entires and exits of every turnstiles in each control area to get the sum of entires and exits for each control area within each time period on each date
3. Averaging the sum of entires and exits for each control area within each time period on each date by control areas and time periods to find **the busiest control areas across time periods with highest average sum of entries and exits** ([Top 20 Busiest Control Areas and Times](images/top20_ca_period.png), [The Distribution across Periods and Days of Top 100 Busiest Control Areas](images/top100_ca_period_heatmap.png), [Top 10 Busiest Control Areas Between 4 pm to 8 pm](images/top10_ca_evening.png), and [Heatmap of control area R533 at Flushing–Main Street Station](images/r533_heatmap.png))
4. Summing the sum of entires and exits for each control area within each time period on each date by time periods and dates to get sum of entries and exits of each time periods on each day
5. Averaging the sum of entries and exits of each time periods on each day by time periods and 7 days of the week to find **the busiest hours across 7 days of the week** ([Periods cross Days Heatmap](images/day_period_heatmap.png))

*The Function of Arrangement Planning*

1. Inputting with the number of outreach weeks, the amount of teams, and the weekly outreach capacity per team
2. Returning a sorted list of the busiest control areas by the rules below:
  1. The list is sorted by the average sum of entires and exits of control areas across time periods
  2. The length of the list will equal to the product of outreach weeks, the amount of teams, and the weekly outreach capacity per team
  3. Each control area will be selected only once per time period on weekdays and only once per time period on weekends
  4. The total numbers of selected control areas in certain time period on certain day of the week will not exceed the product of outreach weeks and the amount of teams 

## Tools
* Python Pandas for ingesting the raw data from [MTA turnstile data](http://web.mta.info/developers/turnstile.html) into csv file
* SQLite3 for creating database and table and importing csv into table
* Python SQLAlchemy for querying from the database into Python
* Python Pandas and Numpy for exploratory data analysis
* Python matplotlib and seaborn for data visualization

## Communication
In addition to the slides of the [final presentation](final_presentation.pdf), [charts](images/), and this written description, the findings will be posted on [my personal blog](https://koscew.github.io/) in the future.