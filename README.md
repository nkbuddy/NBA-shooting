# dsc-phase-3-project-NBA
Final Project Submission<br>
Student name: Qilun Chen, Evan Serrano<br>
Student pace: full time<br>
Scheduled project review date/time: April/1/2022<br>
Instructor name: Praveen Gowtham, Joe Comeaux<br>
Blog post URL:https://github.com/nkbuddy/dsc-phase-3-project-NBA<br>

# Overview
In this project, we are analyzing the data to answer a very simple question: Can we use ML to accurately predict a shot’s success based on external factors that are directly within a coach’s influence?

# Business and Data Understanding
we find a dataset from kaggle, it is about 180,000 shots from 2014 to 2015 NBA.This data contains 21 columns of various datatypes. Some columns were objects that needed to be transformed. There was also an game ID column that was strictly an identifier and contained no other pertinent information. We converted location from object to category. All NaNs were filled by 0 in the dataset.  'GAME_ID','MATCHUP', 'W', 'FINAL_MARGIN', 'SHOT_NUMBER','CLOSEST_DEFENDER','CLOSEST_DEFENDER_PLAYER_ID','PTS','player_name' were dropped as they were not particularly relevant to our analysis. We converted time clock into time elapsed in seconds .We Ceate four categorical feature , includes is 3 point, is open, is dunk or layup, and catch and shot.

# Visualizations
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/correlation%20matrix.png?raw=true)
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/line.png?raw=true)
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/location%20and%20pts.png?raw=true)
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/shot%20dist.png?raw=true)

# Modeling

![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/model%20score.png?raw=true)
we starting with Trees, Bagging, Random Forests, and Boosting. They are basically different implementations of a decision tree, which is the easiest concept to learn and understand. They are also easier to tune, discussed in the next section, than something like SVC. First, we tuned the model with hyper-parameters, than tuned by feature selection.

# Model 1-XGBoost
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/XGB_confusion_matrix.png?raw=true)
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/XGB_feature_importance.png?raw=true)

# Model 2-Random Forest

![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/rf_confusion_matrix.png?raw=true)
![alt text](https://github.com/nkbuddy/NBA-shooting/blob/solved/github%20images/rf_feature_import.png?raw=true)

# Evaluation
XGB classifier have .64 model accuracy after tuning. Time elapsed in seconds, shot disteance, closest defender distance are top three important features. our model is high variance but low bias. Complex question where human error highly unpredictable 

# Conclusion
Need more data like wearable tech or trends from different seasons.
Need more creative feature engineering.
Also, we need some unknown factors like shot angle, streak vs slump, shooter-specific info.
