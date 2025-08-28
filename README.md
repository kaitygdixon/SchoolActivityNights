# SchoolActivityNights
Which weeknights are the busiest for High School Students?

In the Fredericksburg Area, 3 LDS congregations share the same church building for youth groups – we manage this by using the building on different nights. School activities frequently prevent youth from being able to attend activities, sometimes for months at a time, and there has been some debate over which nights are the busiest weeknights for school activities. I decided to problem solve this question with Data Science.

First question – how many high schools and middle schools are attended by youth in these congregations?
High Schools: Massaponax, Courtland, Chancellor, Spotsylvania, Riverbend
Middle School: Thornburg, Spotsylvania, Battlefield, Chancellor, Post Oak, Freedom
All Middle School Sporting events begin at 4pm, therefore they end before youth activities begin at 7pm, making them unnecessary to include in our analysis. We will just focus on the High School Calendars.
Second question – what sports/activities do we need to gather data on?
Orchestra/Band Concerts – only 2 or 3 times per year. Not necessary to include.
Fall: Football, Swimming, Field Hockey, Soccer, Cheerleading, Cross Country, Golf, Volleyball, 
Winter: Basketball, swimming, wrestling, cheerleading, 
Spring: Baseball, Softball, soccer, tennis, track and field, lacrosse,

Third Question -  Where can we gather this data? 
School websites, using webscraping to put them into dataframes.
The key variables are going to be Date, Sport, Time, School, and Roster size. That will allow us to measure which nights have the most frequent activities, and later, weight them by roster size. Ideally, I would like data for at least the 2 previous years, though roster size will likely need to be extrapolated from the current year. 


Data Wrangling: First step – What is the average roster size for each school and each sport, so we know how many youth are affected by that sport?
I started looking through the websites to actually count the roster size, but they didn’t use a common platform, which made retrieval tedious, and since the roster size doesn’t vary that widely, I estimated based on the rosters I did see. I assigned each sport an estimated rosters size.


Webscraping – using BeautifulSoup, I scraped the school calendars from August 2024 through May 2025, obtaining the variables Date, Time, Sport, and School, and I created a dataframe for each of the 5 high schools.
