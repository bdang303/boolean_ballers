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

## Database
After finding several NBA data sources on Kaggle, we created a database including regular season NBA statistics, each teamÕs payroll, and their total wins for the past five seasons. We later built on this database by including playoff data to further our analysis. Database was stored in both CSV and Excel files for our analysis.

## Dashboard
When creating our dashboard we wanted to include data visualizations that were both interactive and communicated our findings clearly. We decided that using Tableau was the best option for creating these data visualizations, especially since we were working with CSV's. It was important to us to demonstrate our results with color-coordinated graphs and that each visualization was easily filtered by season. Below are examples of our dashboard and attached is the link to our Tableau worksheets.
* Playoff results visualization, filterable by season and color-coordinated with team's payrolls
* ![17-18_Playoff_Results](https://user-images.githubusercontent.com/96406929/172761333-739271e0-a9f2-495b-8e12-99d4fd621832.png)
* Scatter Plot showing each NBA Teams regular season wins compared to their payroll, filterable by season
* ![21-22_Wins_Vs_Payroll](https://user-images.githubusercontent.com/96406929/172761533-036c645c-3750-439e-9cab-3e4606d99f48.png)

[link to dashboard](https://public.tableau.com/app/profile/jonathan.moreno6119/viz/NBA_Salaries_and_Stats/RegularSeasonWinsVSPayroll?publish=yes)

## Data Analysis & Machine Learning 

### Hypotheses to test in ML Model

Teams who generally spend more on their payroll are more likely to win more games during the regular NBA season. 

Using the datasets we gathered from various sources and then joined, there were 3 different machine learning models we attempted to utilize to achieve our desired outcome.

### Data Preparation
Prior to feeding the data sets into our models, our group did have to do some slight cleaning. As we pulled our data from fairly reliable sources, there was not a significant amount of effort required to clean the data itself. A few key steps that were taken included:

* Determine which statistical fields from our datasets we wanted to feed into our models as our features. Many of the existing data elements included in our dataset were highly correlated, such as 3-Point Shots Attempted, 3-Point Shots Made, & 3-Point Shot %. We included only made & % to reduce the number of correlated features.
* Data scaling was another key part of our process as the features we included varied in numerical values from 0.01 to 150.00, representing shot attempts as well as percentage ratios. 

#### Linear Regression
Our initial thought was to create a basic model that was trained to take into account 2 features (Team Payroll & Win %). The result was a prediction that for every $1M a team spent on their payroll, would result in a 0.09% Win Rate. Though there was a positive correlation, you can see from the scatterplot below there is a blob of data points congregated in a specific region. We did not believe this approach would provide much value. 

![Linear Reg Graph]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/LinRegGraph.png)

#### Logistic Regression
Rather than trying to determine a numerical predictor, we wanted to predict an outcome, being whether or not a team would make the playoffs based on all these different factors such as Payroll, Average Points Scored Per Game, Wins, Losses, Rebounds, Assists, etc. Because of that, we figured a classifier model was the best accomplish this, and that led us to building a logistic regression model, that resulted in an accuracy score of 53%.

![Logistic Reg Score]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/ML_LogReg_Score.png)

#### Random Forest Classifier
The dataset we were utilizing had over 20 features, and we also wanted to determine which of these features had the highest influence in determining whether or not a team made the playoffs. Based on this requirement, we landed on the approach of using the Random Forest Classifier model which allowed us to rank all of our features, so we went ahead and built that, resulting in a model with a 50% accuracy score.

![Random Forest Accuracy Score]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/Rando_Forest_Score2.png)

Our features ranker determined that Win %, Wins, Loses, obviously had significant influence on whether or not a team made playoffs, however, it was surprising that 3-Point % as well as Payroll also had a reasonable influence.

![Random Forest Ranker]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/RandoForest_FeatureRank.png)

Our model was able to predict with 50% accuracy whether or not a team would make the playoffs based on our features

![Random Forest Confusion Matrix]( https://github.com/bdang303/boolean_ballers/blob/main/Images/ML%20Code%20Shots/Rando_Forest_CMatrix.png))

## Project Website
The purpose of our website is to show the audiences further information for each NBA team for the most recent 5 seasons including this year. Notable features of the website are a directed link to our github repository with 1 click and also a filter function to find desired team by name and season. We also use bootstrap to make the website visually appealing. 

Here are the screenshots of the website

<img width="1675" alt="Screen Shot 2022-06-08 at 6 34 06 PM" src="https://user-images.githubusercontent.com/63434761/172745685-1e2a68dc-f8d7-4001-8ee9-fe4c70908e2b.png">

Screenshot with team name filter applied
<img width="1675" alt="Screen Shot 2022-06-08 at 6 35 12 PM" src="https://user-images.githubusercontent.com/63434761/172745823-5fef2e19-053c-4d71-a2a6-bcbfef6ae5e7.png">

Screenshot with team name and season filter applied
<img width="1673" alt="Screen Shot 2022-06-08 at 6 34 51 PM" src="https://user-images.githubusercontent.com/63434761/172745934-605534c3-7951-4659-afe2-a36a8aee2ac1.png">


## Conclusion  
The results indicated that we can predict whether a not a team would make the playoffs with 50% accuracy rating via the Random Forest ML that we used. While this is a decent accuracy score, we are forgetting very important concepts to the game of Basketball. For starters, the stats that we used were mainly focused around the offensive side of the ball and fail to take into account things such as defensive efficiency. These stats are very important to predicting how a team will react when faced with different adversity. We also fail to indicate the advantages of being home or away which provide players with more comfort and slightly more rest. Lastly, we have no way of telling what the impact of injured or absent players are. If our biggest star were not playing, our ML has no way of factoring in that disadvantage. Even so, we believe that this model can be tuned up to add these additional factors, while maintaining a high level of accuracy. 


## Data Source(s)

- NBA Play Salary Data (2021 - 2022 Season & Beyond)
- NBA Team Standings, Wins, Lossess (2016 through 2021 NBA Regluar Seasons)

## Presentation
 - https://docs.google.com/presentation/d/1jhaM10uesy7SOXLdY-P-Jz-0pnyyfjaD/edit?usp=sharing&ouid=111472340599065338820&rtpof=true&sd=true

