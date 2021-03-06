# FinTech-Project-1
## FinTech Project 1

# Project Title
## Soccer "Money" Ball Fantasy Football

![Soccer Money Ball](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Soccer_Money.png?raw=true)"

# Team Members
- Adam Freeman
- Marcus Whitelock

# Project Description/Outline

- ### Could we use our programmings skills to create the greatest fantasy football team and win the big money prizes !

- ### Could we create this based on stats alone ?

- ### Does a team of champions create a champion Team ?

- ### Doing this programmatically, does this mean we can repeat this code not just for one league but for many leagues, which means many more chances to win

- ### Can we become the most feared Football fantasy team on the globe and 

- ### All these questions and more will be answered with our projects **Soccer 'Money' Ball Analysis**.

# Analysis Report
## We Need DATA ! But what data and where is it??

Initially the team focussed on finding suitable datasets that could provide the information required for this project. After significant research the following data sets were chosen
- Kaggle 
    - European Soccer Database - [Euro Soccer Database - SQLDBlite Database](https://www.kaggle.com/hugomathien/soccer)
- API-FOOTBALL 
    - [API-FOOTBALL - RapidAPI API](https://rapidapi.com/api-sports/api/api-football)
- ISO.org 
    - [ISO.org CSV File](https://www.iso.org/obp/ui/#search)

It was a deliberate decision to choose 3 different data types and data sources in order to demonstrate the teams skills and adaptability across 3 very common data set types you would expect to encounter in real world FinTech scenarios. These data source types are CSV files, Databases and APIs.

The following details these data sets and the steps undertaken to be able to utilise them for this project. 

1. Database - European Soccer Database 
    -  This dataset was found on the Kaggle online community. This data set is available as an SQLiteDB file. The team was able to complete the following tasks on this database to make it useful to our project. 
    - Download the SQLLiteDB file
    - Open the file and inspect the table structure, recreate the database schema.
    - Create a new postgress database and apply the schema generated by the team. The Database ERD can be seen below
    ![Euro Soccer DB - Zoomed](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Euro_Soccer_ERD_Zoomed.PNG?raw=true)
    - Export the data into sql seed files and create the postgresql queries to seed the database with all data.
    - Clean the data as required to fix many constraint issues and missing data.

2. API -  API-FOOTBALL
    - We created a Rapid-API account and subscribed to the API-Football. This is a paid subscription and a shared set of credentials was disseminated to the team allowing all members access to the API data.

3. API - FutDB
    - We created a FutDB account and subscribed to the API. This is a paid subscription and a shared set of credentials was disseminated to the team allowing all members access to the API data.
    
4. CSV -  ISO.ORG
    - We wish to include information in our reports which requires us to have a consistent and accurate data set for country and region codes and names. The Country Codes CSV file provides us the data we require and is the accepted point of truth for such data.
    - This data was copied into a Excel worksheet, examined and then saves as a CSV file.
 

## We have data ! Lets see what we can do with it.

Before we start tacking some more advanced queries and visualizations we decided to do some ground work first. Before we can reach our Soccer "Money" Ball goal we need to familiarize ourselves with the world football landscape. 

We utilized our database to produce some base visualizations to give us some context of what we were working with. 

### What are the biggest Leagues in the World and How many Games do they play

![Total_Matches_Per_League](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Total_Matches_Per_League.PNG?raw=true)

This visualization helped us determine that there are 4 leagues that play more games then the others. The is important to us as more games means more players and more competition and therefore more opportunity. 

We decided to create an interactive plot to inspect the total matches per league to see if they were consistent or changed for different leagues over different years. 

![Total_Matches_Per_League_Per_Year](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Total_Matches_Per_League_Per_Season.PNG?raw=true)

 ### Lets look at goals scored, are different leagues more attacking or defensive ?

We decided to look at a number of factors regarding which leagues or years are more attacking. This can help us determine which leagues we can focus on and understand the trend of goals yer to year.

![Total_Goals_Per_Season_All_Leagues](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Total_Goals_Season_All_Leagues.PNG?raw=true)

We determined that there was a small deviation for total goals year to year, but interestingly there was a slight correlation of an increase in average goals scored per game per season as the years increased. 

 ### If a goal is the ultimate measure of currency in soccer then lets look at any factors that could influence the number of goals

 Lets look at it is more likely for the home team to score.

 ![Average_Home_VS_Away_Goals_Scored_All_Leagues_Seasons](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Average_Home_VS_Away_Goals_Scored_All_Leagues_Seasons.PNG?raw=true)

The PIE chart above averages all home vs all away goals scored for all seasons and all leagues. This demonstrates that there is a definite home team advantage. This information is very good to know. 

 ### Does the amount of home vs away advantage change per season ?

 ![Average_Home_VS_Away_Goals_Scored_All_Leagues_Per_Season](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Average_Home_VS_Away_Goals_Scored_All_Leagues_Per_Season.PNG?raw=true)


 ### Does the amount of home vs away advantage change per league ?

We were able to create average home and away goals visual for all seasons for each league. The drop down allowed us to analyse each league and see which are more attacking and more defensive

 ![Average_Home_VS_Away_Goals_Scored_Per_League_Per_Season](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Average_Home_VS_Away_Goals_Scored_Per_League_Per_Season.PNG?raw=true)

 ### Where do these Soccer players come from is it truly a global sport ?

 We questioned ourselves, was this the right sport to target ? Is it truly a global sport with high participation. We were able to create a global map of all countries and highlight all countries that are the country of birth of a professional soccer player. It is evident that soccer is truly a global sport. 

  ![Footballers_Country_Of_Birth](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Footballers_Country_Of_Birth.PNG?raw=true)

To extend this idea, we decided complete some additional plots to allow us to review some more metrics for this world sport. 

 ![Number_Of_Leagues_Per_Country](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Number_Of_Leagues_Per_Country.PNG?raw=true)

This plot shows the number of leagues per country. It can see that there is a number of professional leagues all around the world with higher numbers of leagues in Brazil and Europe.


# We get the data now lets play soccer "money" ball

From the ground work we completed we now have a better understanding of the data. Through this process we narrowed our scope to the following leagues
- English Premier League
- Italy Serie A
- France Ligue 1
- Spanish LIGA

We know these are the most attacking leagues and play the most games. We also understand that there is a definite home team advantage, and there is a loose trend of more goals being scored this year then the previous year. We have also confirmed that Soccer is truly a global sport played in many countries and represents a good choice of sport as there will be many fantasy football competitions across the globe we can enter. 

Using all of this data we have assembled the following fantasy football teams for each of the 4 Top Leagues using programatic statistical analysis only !


## English Premier League

### Plot field with Players
 ![EPL_fantasy_team](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Prem_Fantasy_Team.png?raw=true)


### Player Statistics
 ![EPL_fantasy_team_player_stats](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/EPL_fantasy_team_player_stats.PNG?raw=true)

## France Ligue 1

### Plot field with Players
![Ligue1_fantasy_team](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Ligue1_Fantasy_Team.png?raw=true)

### Player Statistics
 ![Ligue1_fantasy_team_player_stats](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Ligue1_fantasy_team_player_stats.PNG?raw=true)

## Italy Serie A

### Plot field with Players
![Seria_fantasy_team](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/SerieA_Fantasy_Team.png?raw=true)

### Player Statistics
 ![Seria_fantasy_team_player_stats](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/Seria_fantasy_team_player_stats.PNG?raw=true)

## Spanish LIGA

### Plot field with Players
![LaLiga_fantasy_team](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/LaLiga_Fantasy_Team.png?raw=true)

### Player Statistics
 ![LaLiga_fantasy_team_player_stats](https://github.com/apfreeman/FinTech-Project-1/blob/main/Images/LaLiga_fantasy_team_player_stats.PNG?raw=true)







