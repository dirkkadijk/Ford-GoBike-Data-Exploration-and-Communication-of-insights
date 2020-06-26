# Ford-GoBike-Data-Exploration-and-Communication-of-insights

## 1. Investigation Overview

This project has two parts that demonstrate the importance and value of data visualization techniques in the data analysis process which is as Capstone project part of the Udacity Data Analysis Nanodegree course.

- In the first part (1/2) I used Python visualization libraries to systematically wrangle and explore the origin `2017-fordgobike-tripdata` datafile, starting from plots of single variables and building up to plots of multiple variables.

- In this second part of the project (2/2), I present slides with visualizations the interesting relationships, patterns and insights that I discovered in the (in part 1) selected and cleaned dataset.



## 2. Dataset Overview

Bay Wheels is the first regional and large-scale bicycle sharing system deployed in California and on the West Coast of the United States. As of January 2018, the Bay Wheels system had over 2,600 bicycles in 262 stations across San Francisco, East Bay and San Jose. 

On June 28, 2017, the system officially re-launched as Ford GoBike in a partnership with Ford Motor Company. After Motivate's acquisition by Lyft, the system was subsequently renamed to [Bay Wheels](https://www.lyft.com/bikes/bay-wheels) in June 2019.  The system is expected to expand to 7,000 bicycles around 540 stations in San Francisco, Oakland, Berkeley, Emeryville, and San Jose.

The dataset used for this exploratory analysis consists of Bay Wheels's trip data for individual rides made in a bike-sharing system covering the greater San Francisco Bay area from June 28, 2017 to December 31, 2017. The original dataset `2017-fordgobike-tripdata.csv` can be found in the download [here](https://www.lyft.com/bikes/bay-wheels/system-data).

The Dataset consists of anonymized information regarding 519.700 bike trips, including its timing and geolocation of the start and end of each trip. 


## 3. Wrangle/Clean to create cleaned datafile `fordgobike-tridata_clean.csv` (part 1)

For safety and to enable bi- and multivariate exploration I removed the outliers with values beyond 5 standard deviations based on calculated Z-score. 
As a result all observations with bike trip duration_min > 44 minutes were removed. 

Further we created several start_variables with different time-resolution (start_hour_of_day, start_day_of_week, start_month). Plus corrected some data_types.

In the data exploration we used mainly the following features in the cleaned datafile `fordgobike-tridata_clean.csv`:

>- user_type (values: “Subscriber” or “Customer”)
>- duration_min (duration of trip in minutes) 
>- start_date  (date of start of biketrip) 
>- start_hour_of_day  (hour of start of biketrip) 
>- start_day_of_week  (day of week of start of biketrip) 
>- start_month  (month of start of biketrip) 



## 4. Summary of Findings of Data Exploration (part 1)

In the exploration I found regarding the main variables of interest:
- Definitely each of these graphs reinforces the general hypothesis that customers are more like recreational users and subcribers tend to be people that use them to go to work or school:
  - Subscribers mainly hire a bike during weekdays (more than double the level of weekdays), and Customers hire especially in the weekend.
  - The bike trip duration of Customers is about the double of Subscribers (18 vs 10 minutes).
  - A significant higher trip duration during weekend days by Customers. The duration is about 18.5 minutes during weekend days, which is about 10% higher than the highest score during a weekday.
- But the last (multivariate explorations) help us get even more detail about the patterns of use on hourly level over the whole course of a week, and the differences between Customers and Subcribers.
  - For both types of users the distribution of rides during the weekdays depends a lot on the hour of the day and day of the week. 
  - It is interesting, that Customers tend to use the bike service mostly on Saturday/Sunday from 12 PM to 5 PM, while Subscribers will likely have a trip from Monday to Friday during rush hours (8-9 AM, 17-18 PM).

Outside of the main variables of interest, I found:
- Also location of end destination station matters as variable for predicting bike usage; the destination `The Embarcadero at Sansome St` has the highest trip duration (about 30-40% higher) compared with other destinations. This has probably a relation with that the station is located at a great tourist/recreation area which ... can make you understand why the bike trips by Customers take long... :)


>Note: The Data Exploration has been done in notebook `exploration_GoBikes_by_DirkKadijk1.0.ipynb`.


## 5. Key Insights for Presentation slides (part 2)

In the presentation I focus on the relationship between bikes ride count and trip duration and user_types (Customers, Subscribers).

I start with a barchart visual with the distribution of trip count between the 2 user_types. 

Followed by the distribution of biketrip duration for each user_type (2 histograms side-by-side).

Then I present a heatmap of the count of bike trips by both hour-of-day and day-of-week for each user_type (visuals side-by-side). This gives a clear view of bike usage over the course of a weekprofile (heatlevel for each of the 7x24 hours) and gives much insight about the difference in bike usage profile between the 2 user_types.

Finally I present a clustered barplot of trip duration by both start_day_of-week and end_station_name (limited to the top 10 end stations). This illustrates that also the location of the end destination station matters as variable for explaining bike usage and trip duration.


>Note: click on the file 2_slide_deck_GoBikes_by_DirkKadijk1.0.slides.html to start the interactive prosentation which is in a Jupyter notebook is a HTML slide format (based on reveal.js library). Click of navigate to left/right/up/down to see all (optional) slides and press ESC for overview of slides.
