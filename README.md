# Predicting the success of Kickstarter projects 
University of Jyväskylä TIES445 data mining project, Janne Mäyrä and Riikka Vilavaara

## Research question
Based on the data of all previous Kickstarter projects, are we able to predict the success of currently live projects. How about number of backers they get, or the amount of money they will raise?

## Data

Webrobots.io [hosts scraped Kickstarter data](https://webrobots.io/kickstarter-datasets/). In this project we are using data dated 2018-02-15.

Before any modifications or selections, total size of this dataset is 195614 projects and 37 features. 

There are 105680 successful projects, 73634 failed projects, 8823 cancelled projects, 601 suspended projects and 6876 live projects. In this project, we drop canceled and suspended projects 

## Workflow

### Question
There are three different features to predict:
1. Success/failure
2. Number of backers
3. Amount of money raised

Of these we focus on Success/failure. Number of backers and amount of money can be predicted for instance with regression tree forests, but they might need data from different rewards. We tested those and got really bad scores.

### Data acquisition
[Data preprocessing](Data%20preprocessing.ipynb) - Processing the data downloaded from webrobots.io so it can be explored

### Exploration & Preprocessing
[Exploring the data](Data%20exploration.ipynb) - Finding out what kind of data we have, and what should be done before modelling
* Main problem is incomplete data with scewed success/failure rate in the training set
* Some of the data may need normalization/standardization

[Processing data](Processing%20Data.ipynb) - Processing the explored data to prepare it for modelling
* Changing categorical values to numerical
* Removing some of the outliers and unnecessary values
* Standardizing some of the values

### Model
Use RandomForestClassifier for Success/failure.

Build a classifier, test different hyperparameters, drop irrelevant keys.
[State classifier](State%20classifier.ipynb)

Try to apply PCA to processed dataset:
[State classifier with PCA](State%20classifier%20with%20PCA.ipynb)

### Results

Try to classify live projects and try to compare the results to real information if the project is finished.

[Live project predictor](Live%20project%20predictor.ipynb)

Out-of-box error for classifier is ~0.21, while accuracy score for live projects is around 64%. 