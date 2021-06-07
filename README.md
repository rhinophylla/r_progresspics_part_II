# /r/progresspics Project Part II

### Project Goals

r/progresspics is an active subreddit where people post before and after pictures that document weight change, typically weight loss.  The goal of this project is to create a dataset of features extracted from r/progresspics titles and metadata and then use these features to develop a model that can predict the final weight as described in a post title.

### Previous efforts

This project is a continuation of one of my previous projects, "r_progresspics".  That project extracted a more limited set of features from r/progresspics post titles, summerized the characteristics of r/progresspics posters, and used linear regression to try and deterimine which of the features explained variation in the amount of weight lost and/or the popularity of individual posts.  That project can be found here:  https://github.com/rhinophylla/r_progesspics

### Contents of repo

Currently this project is contained within 5 Jupyter notebooks of Python code.   

**01_primary_feature extraction**:  Redditors are instructed to post to r/progresspics using a recommended title format that includes their sex, age, height, starting weight, ending weight and how long the weight change took.  The code in this notebook extracts this information from the title string, cleans the data, and organizes it in a dataframe.

**02_feature_engineering**:  This notebook contains code that creates additional features from other post information.

**03_feature_exploration**:  This notebook contains code that creates plots exploring each feature and its relationship with the target.

**04_model_exploration_and_training**:  This notebook contains code that prepares the extracted features then tests a wide variety of regression algorithms using cross validation to see which one is the most effective at predicting the final weight of the r/progresspic posters.  Effectiveness is judged by comparing the RMSE of each model to all other models as well as several baseline models.  The top three models are further explored using learning curves and feature importance and improved with hyperparameter optimization.

**05_final_model_testing**:  The model identified during training as the "best" is used on the previously set aside testing data.

### Results

My efforts created a random forest model that predicts the final weight of a r/progresspics poster with a RMSE of 20.29 and a R2 of 0.8.  The RMSE of the median baseline model is 45.70 so this trained model does a significantly better job than using the median of the population's end weight to predict the final weight of an individual poster.

### Coming soon

1. Stand alone python scripts
2. Final report detailing my process and results
