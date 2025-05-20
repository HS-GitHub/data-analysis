# Data-Analysis

Google Capstone Case Study: Cyclistic Bike-Share Analysis


Introduction
The Cyclistic Bike Share Case Study is a capstone project for the Google Data Analytics Professional Certificate on Coursera. In this project, I will follow the data analysis process which I learned from the course: Ask, Prepare, Process, Analyze, Share and Act to analyze the data.

Background
In 2016, Cyclistic launched a successful bike-share offering. Through the years, the program has expanded significantly to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station within the network at their convenience. 

Cyclistic’s marketing strategy so far relied on building general awareness and appealing to broad consumer segments. The company offers flexible pricing plans that cater to diverse needs of users including single-ride passes, full-day passes and annual memberships. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.

The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, as a data analyst my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, team will design a new marketing strategy to convert casual riders into annual members.

Approach/Steps

1. Ask

Business Task - design marketing strategies to convert casual riders to members by understanding how annual and casual riders differ. Maximizing the number of annual members will be key to future growth of the company
Key tasks :
  * Identify the business task
    - convert casual riders into members
  * Consider key stakeholders
    - Director of marketing
    - Cyclistic Manager 
    - Cyclistic marketing analytics team
    - Cyclistic executive team
    
2. Prepare

   * Data Source
     - Divvy_Trips_2019_Q1
     - Divvy_Trips_2020_Q1
     - Divvy_Trips_2025  
[Note: the data has been made available by Motivate International Inc. under license]
 
* Tools
    - Data cleaning & processing - SQL on Big Query and Google sheets
    - Data visualization - Tableau


3. Process
The basis for this analysis is Feb/March 2025 data and the steps for processing the data are as follows:

  1) Data Combining

SELECT * FROM `inlaid-marker-454718-q1.CyclisticData.Cyclistic_2025` AS march
FULL JOIN `inlaid-marker-454718-q1.CyclisticData.cyclisticDataMarch` AS feb
ON march.ride_id = feb.ride_id


The 2 tables for the month of February and March were JOIN together into a single table. The table consists of 450035 rows.

Data Exploration
I ran the queries for each column to understand any errors, missing value , inconsistencies and determine the data type.

No.
Variable
Description
1
ride_id
Unique ID assigned to each ride
2
rideable_type
Classic, docked or electric
3
started_at
Date and time at the start of trip
4
ended_at
Date and time at the end of trip
5
start_station_name
Name of the station where the bike ride journey started from
6
start_station_id
ID of the station where the bike ride journey started from
7
end_station_name
Name of the station where the bike ride journey ended at
8
end_station_id
ID of the station where the bike ride journey ended at
9
start_lat
Latitude of starting station
10
start_lng
Longitude of starting station
11
end_lat
Latitude of ending station
12
end_lng
Longitude of ending station
13
member_casual
Type of membership of each rider




Data Cleaning
The data has been cleaned before analysis, by following steps 
Removed duplicates and trips with null values
Adding 3 columns: ‘ride_length_in_mins’,’day_of_week’ and ‘month’
Sort and filter the data 

SELECT
 april.member_casual,
 april.start_station_name,
 COUNT (april.ride_id) AS no_of_rider
FROM inlaid-marker-454718-q1.CyclisticData.Cyclistic_2025 AS april
GROUP BY
  april.member_casual, april.start_station_name
ORDER BY
 no_of_rider ASC


       A summary of your analysis
Casual member in April ’25 = 85869
Member in April ’25 = 212286
Casual member in March ’25 = 27754
Member in March ’25 = 124126
There are more than 300 stations with a singer rider as casual or member of Cyclist


Analyze

Data Analysis
	The cleaned data was imported in Tableau for analysis and the finding are summary as  
             Below – 

Cyclistic Member and Casual Bikers total for the month of Feb/March 2025

Count of Casual bikers : 8,984
Count of Member bikers : 33,002


                                                  
  


Type of Bikes

There are two types of bicycles: Classic, electric
Electric bikes are more popular among members and casual riders over Classic bikes 
                                  




Trips taken in a Week

Cyclistic members have the greatest activity on Wednesday and lowest movements on Mondays
Casual riders have highest activity on Saturdays and lowest activity on Thursdays





 Cyclistic Member/Casual Count on Start Stations 

MAX member biker count is on Ravenswood station : 451
MAX casual biker count is on Sheridan Road station : 124

                   


Average Ride Duration in Minute

Average bicycle ride for members is about 25 minutes whereas casual bike riders have an average ride length of 15 minutes. Hence, the ride duration of Cyclist members are approximately two times smaller than casual riders.
               

	
Share


	Similarities:
Both Cyclistic members and casual riders prefer electric bicycles over classic bicycles 
Both Cyclistic members and casual riders have higher average ride duration on the weekends as compared to on weekdays
	Differences: 
Cyclistic members go on more rides than casual riders. 
Cyclistic members have a larger average ride length (25 minutes) than casual riders (15 minutes). are more active on weekdays
Cyclistic members are having consistent rides throughout the week which is on peek on weekend while casual rides are more active during the weekdays 


Act 
Recommendations
Based on the above analysis, the marketing strategies to convert casual riders to Cyclistic members can leverage following approach: 

Seasonal campaigns
Introduce seasonal campaigns by offering special weekdays offers, limited time discounts appeal to casual riders. 
Group Membership Discounts
Offer discounted plans for friends, students and families can encourage 
collective membership. 
Membership Loyalty Points System
Implement a membership loyalty points system for users to collect points for each ride and rewards such as membership discount.
Social Media Engagement
Leverage digital media, including media platforms to engage with both casual riders and members by creating content to promote the joy of bike riding.  

