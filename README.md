# Boolean_Ballers

## Overview

Project is centered around sports analytics with a focus on data from the National Basketbal Association (NBA). Our goal is to determine if there is any correlation between NBA players' salary per team, and wins during the regular season and post season. We also want to be able to look at various statistics within a basketball team and see if there's a certain stat that provides teams with more success, I.E. FGA, 3P%, ASTs. We selected this topic because we want to see what the potential outcomes for future teams might be based on statitics of players and team salary. Furthermore, we feel that based on this data we can potentially predict Win PCT and post season outcomes a year prior to the results. 

## Questions We Want to Answer
* Is there a strong correlation between Team Salary and Win PCT?
* Is there a strong correlation between Team Salary and Post Season Success?
* Is there a specific statistic that provides a team with a better chance to win?

## Group Communication Protocols
* Throughout the length of this project our group was committed to checking slack a minimum of once a day and meeting 3 times a week.
* In our meetings we were to share the work that we had done in the days prior and go over action items for everybody to finish by the next meeting. 

**Team Responsibilities**
* Bobby Dang - Github and advanced ML
* Zach Pausa - Data gleaning and early ML
* Khanh Nguyen - HTML Website 
* Jonathan Moreno - Database and Tableau 

## Topic Details

Using multiple datasets with data elements on NBA Player salaries, as well as win totals from the 2016 through 2021 NBA Regular Seasons, our project hopes to outline an algorithm that predicts whether or not a team will make the playoffs to contend for a championship, based on player salaries with a combination of other team statistics. 

## Getting Started
We started the project by getting data from various cites. Afterwards we put them into csv files named "NBA_Salary", "nba_team_stats_00_to_21" and "NBA_Player_Salaries". After combining several columns of data into "NBA_Salary" Once we merged the data to one CSV we were able to create one column as an X axis and another as a Y axis. From there we went into the Machine Learning stage of the project. 

## Data Analysis & Machine Learning 
Using the datasets we’ve gathered and joined, there were 3 different machine learning models utilized to achieve our desired outcome:

### Linear Regression
This was a basic model that was trained to take into account 2 features (Team Payroll & Win %). The result was a prediction that for every $1M a team spent on their payroll, would result in a 0.09% Win Rate. 

![Linear Reg Graph]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/LinRegGraph.png)

### Logistic Regression
With a classifier model, we wanted to determine an outcome, being whether or not a team would make the playoffs based on a number of features such as Payroll, Win %, Points, Rebounds, Steals, etc. Our model resulted in an accuracy score of 53%

![Logistic Reg Score]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/ML_LogReg_Score.png)

### Random Forest Classifier
The Random Forest model ended up being our preferred model as we were able to achieve an accuracy score of 97%. In addition, we were able to utilize this model to rank the features and how each metric influenced whether or not a team made the playoffs. 

![Random Forest Ranker]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/RandoForest_FeatureRank.png)

## Database
After finding several NBA data sources on Kaggle, we created a database including regular season NBA stastics, each teams payroll, and their total wins for the past five seasons. We later built on this database by including playoff data to further our analysis. Database was stored in both CSV and Excel files for our analysis.

## Project Website
The purpose of our website is to show the audiences further information for each NBA team for the most recent 5 seasons including this year. Notable features of the website are a directed link to our github repository with 1 click and also a filter function to find desired team by name and season. We also use bootstrap to make the website visually appealing. 

## Conclusion  
The results indicated that we can predict win percentage with a 95% accuracy rating via the ML that we created. While the accuracy rating is high we are forgetting very important concepts to the game of Basketball. For starters, the stats that we used were mainly focused around the offensive side of the ball and fail to take into account things such as, rebounds, steals, and defensive efficiency. These stats are very important to predicting how a team will react when faced with different adversity. We also fail to indicate the advantages of being home or away which provide players with more comfort and slightly more rest. Lastly, we have no way of telling what the impact of injured or absent players are. If our biggest star were not playing, our ML has no way of factoring in that disadvantage. Even so, we believe that this model can be tuned up to add these additional factors, while maintaining a high level of accuracy. 


## Data Source(s)

- NBA Play Salary Data (2021 - 2022 Season & Beyond)
- NBA Team Standings, Wins, Lossess (2016 through 2021 NBA Regluar Seasons)

## Presentation
 - https://docs.google.com/presentation/d/1jhaM10uesy7SOXLdY-P-Jz-0pnyyfjaD/edit?usp=sharing&ouid=111472340599065338820&rtpof=true&sd=true

## Hypotheses to test in ML Model

Teams who generally spend more on their payroll are more likely to win more games during the regular NBA season. 

## Testing
