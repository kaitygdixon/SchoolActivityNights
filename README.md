# School Activity Nights Analysis
This project analyzes public school sports calendars to understand student availability for weeknight youth activities.

In the Fredericksburg Area, 3 LDS congregations share the same church building for youth groups – we manage this by using the building on different nights. School activities frequently prevent youth from being able to attend activities, sometimes for months at a time, and there has been some debate over which nights are the busiest weeknights for school activities. I decided to problem solve this question with Data Science.

## Project Overview
- Goal: Identify which weeknights students are busiest with extracurriculur sports
- Data: Publicly available high school athletic calendars
- Output: Cleaned dataset and visualizations
- Key Insight: Wednesday is the busiest night, largely due to football, track, and cross country

## First question – how many high schools and middle schools are attended by youth in these congregations?
High Schools: Massaponax, Courtland, Chancellor, Spotsylvania, Riverbend
Middle School: Thornburg, Spotsylvania, Battlefield, Chancellor, Post Oak, Freedom
All Middle School Sporting events begin at 4pm, therefore they end before youth activities begin at 7pm, making them unnecessary to include in our analysis. We will just focus on the High School Calendars.

## Second question – what sports/activities do we need to gather data on?
Orchestra/Band Concerts – only 2 or 3 times per year. Not necessary to include.
Fall: Football, Field Hockey, Soccer, Cheerleading, Cross Country, Golf, Volleyball, 
Winter: Basketball, swimming, wrestling, 
Spring: Baseball, Softball, soccer, tennis, track and field, lacrosse,

## Third Question -  Where can we gather this data? 
School websites, using webscraping to put them into dataframes.
The key variables are going to be Date, Sport, Time, School, and Roster size. That will allow us to measure which nights have the most frequent activities, and later, weight them by roster size. Ideally, I would like data for at least the 2 previous years, though roster size will likely need to be extrapolated from the current year. 

## Data Wrangling: First step – What is the average roster size for each school and each sport?
I started looking through the websites to actually count the roster size, but they didn’t use a common platform, which made retrieval tedious, and since the roster size doesn’t vary that widely, I estimated based on the rosters I did see. I assigned each sport an estimated rosters size.

## Webscraping 
Using BeautifulSoup, I scraped the school calendars from August 2024 through May 2025, obtaining the variables Date, Time, Sport, and School, and I created a dataframe for each of the 5 high schools, then combined it into one dataframe.

## Exploratory Data Analysis
There were a lot of duplicates and extra events scraped from the school calendars, so I cleaned and validated by standardizing time, filtering out events that didn't overlap with youth activity times, and removing duplicates. I also added a season filter, so open gyms that are on the calendar but are outside standard sports seasons are dropped. 

## Evaluation and Results
I added an average roster size column to the cleaned data, and analyzed the weeknight distribution of sports events, weighted by participation. The results were visualized both in cumulative student-nights by weeknight, and in average participants busy on that weeknight throughout the year. To find the average, I did account for days without sports events. 

## Deliver and Document
I created an executive summary to be distributed among church youth group leaders in the 3 congregations, to inform them of the results of analysis, with the recommendation that although Wednesdays are busier, I advise them to stay with the same youth nights, not alternate, because the difference in youth group attendance between the 3 nights is so small.

