# Predicting the success of Kickstarter projects 
University of Jyväskylä TIES445 data mining project

## Research question
Based on the data of all previous Kickstarter projects, are we able to predict the success of currently live projects. How about number of backers they get, or the amount of money they will raise?

## Data

Webrobots.io [hosts scraped Kickstarter data](https://webrobots.io/kickstarter-datasets/). In this project we are using data dated 2018-02-15.

Before any modifications or selections, total size of this dataset is 195614 projects and 37 features. 

There are 105680 successful projects, 73634 failed projects, 8823 cancelled projects, 601 suspended projects and 6876 live projects. In this project, we consider also cancelled and suspended projects as failed.

## Workflow

### Question
There are three different features to predict:
1. Success/failure
2. Number of backers
3. Amount of money raised

### Data acquisition
Get the data from webrobots.io

### Exploration
Find out what kind of data we have, what is irrelevant, possible outliers, what preprocessing the data needs before modelling

### Model
Use RandomForestClassifier for Success/failure and RandomForestRegressor for number of backers and amount of money raised.

### Results

Try to classify live projects and try to compare the results to real information if the project is finished.


## asdf

- Data preprocessing, I: [Data preprocessing ](Data preprocessing.ipynb) - Processing the data so it can be explored
- Data preprocessing, II: [Exploring the data](Data exploration.ipynb) - Finding out what kind of data we have, and what should be done before modelling
- Data preprocessing, III: [Processing data](Processing data.ipynb) - Processing the explored data to prepare it for modelling
 - Changing all values to numerical
 - Removing outliers and unnecessary columns
 - Standardizing some of the values
 
- Modelling: 
- 