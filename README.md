![image](https://github.com/prollin2/FORBES-Most-Valuable-Franchises/assets/147635504/173e4014-de4a-47cb-b649-bd095bb4fa24)

# FORBES-Most-Valuable-Franchises
FORBES Most Valuable Franchises - Does Sport/League Contribute to Higher Valuations?


# Introduction

  The purpose of this project is to explore the Forbes Most Valuable Sports Teams in the World ranking, and gain an understanding of how league (NFL, NBA, MLB, Premier League, etc.) influences valuation. Each year, Forbes looks at sources of revenue (net equity plus debt), historical transactions (i.e. how much the team was bought for and when), and stadium economics when calculating their valuation estimates for each team and ranks them. When I observed this ranking, I became interested in how the league each team participates in influences their value/ranking. Are NFL teams more likely to be in the top 50? Does the influence of Middle East Oil money in European soccer leagues have a significant impact on their valuation? I will explore these questions and more in my analysis.


# Rationale

  Given the valuation for each other top 50 teams/franchises, I will explore their breakdown by league with some exploratory visualizations (barplot/boxplot). Through this I can identify any preliminary trends in the rankings, and create a hypothesis before making any models. After I create my hypothesis, I will run a multiple regression to see at a basic level how each league contributes to the overall valuation of a team. To do this, I can create dummy variables for each league so the regression model can differentiate between each league. I will then test an XGboost regression model to see if I can produce better results than the multiple regression model. I will then assess the accuracy of the model by finding the RMSE, MAE, and R^2 for the regression model.
  
# Methods

  I started by running a multiple regression with value as my prediction variable and league as my x-variable. This means I had to make dummy variables for each league so they could be differentiated in the model. I split the dataset into a training and testing set (80% train, 20% test), and identified league as our y-variable with league being our x-variable. I ran an XGboost training model to determine the most effective number of rounds (identified with the lowest test-rmse) which turned out to be 15 rounds. After running my XGBoost model, I tested its accuracy/efficacy by find the RMSE, MAE, and R^2 for the regression model. For these metrics, I want the RMSE and MAE to be low and the R^2 to be close to 1 which would signify a well-built model.


# Findings

  When looking at the results from the multiple regression model, I can determine that soccer has a higher coefficient than any other league in contributing to overall valuation (coef = 1.4166). This means that for every team that plays in a soccer league, their valuation increases by $1.4166 billion. However, the caveat with this model is the R^2 which is 0.061. This signifies a very weak positive fit from our model to the data. Also, each league is not significant in our model as their p-values are greater than my alpha of 0.05. I wanted to improve upon this model with an XGBoost regression model that hopefully could improve its R^2. 
  The results from the XGBoost model did not provide better results as its R^2 was equally as poor as the multiple regression. What can be determined from this is that in order to truly understand the impact league has on a team's valuation, I need to find more data that identifies revenue streams, stadium finances, and other financial statistics to factor them into my models. Rather than looking at league holistically, I should be breaking it down to identify what it is that makes each league more valuable than the others. 
  Based on my exploratory evaluations, I can identify that the NFL reigns supreme over other leagues with 30 of its 32 teams being within the top 50. Through more research, I found that soccer clubs have had more movement than any other league in the top 50 indicating that a change is being made in the way soccer clubs are managed and marketed. My next steps would be to analyze the way the NFL markets itself and its television deals comparative to European soccer leagues. Why are American leagues so dominant in the sports industry? Can it be replicated overseas?
