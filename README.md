# soc-data
This project was done at an internship at [TerraNexum](https://www.terranexum.com/)
## Libraries and datasets used
### Data
* [1.6 million labeled tweets](https://www.kaggle.com/datasets/kazanova/sentiment140)
* Self-labeled training/testing data - See [Twitter.ipynb](https://github.com/terranexum/soc-data/blob/main/notebooks/Twitter.ipynb)
### Libraries
*
*
*
## Overview
The primary objective is to develop a sentiment analysis model that can accurately classify tweets based on their sentiment. 
The notebooks are structured as follows:

1.	Retrieve [(Twitter.ipynb)](https://github.com/terranexum/soc-data/blob/main/notebooks/Twitter.ipynb): Connect to the Twitter API to retreive tweets
    
2.	Manual Classification [(label.ipynb)](https://github.com/terranexum/soc-data/blob/main/notebooks/label.ipynb): This notebook allows users to manually classify the retrieved tweets into different sentiment categories.

3.	Sentiment Analysis Model - large training data [(new data classifying large.ipynb)](https://github.com/terranexum/soc-data/blob/main/notebooks/new%20data%20classifying%20large.ipynb): Train and evaluate a model trained off of 1.6 million tweets

4. Sentiment Analysis Model - small training data [(new_Data classifying small.ipynb)](https://github.com/terranexum/soc-data/blob/main/notebooks/new_Data%20classifying%20small.ipynb): Similar to the former, train and evaluate model trained off of only 100 tweets

## Twitter.ipynb
> NOTE: this code requires "Basic" teir access to the X (fka Twitter) API as of July 2024
>
> For more info click [here](https://developer.x.com/en)

Using Tweepy and the Twitter API, this code allows for the user to retreive up to 100 tweets at a time. The user first authenticates using a bearer token and designs a query to their liking. The retrieved tweets are stored in a list and then printed for inspection. The script ensures all tweets are appended correctly to the list for further processing. A Pandas DataFrame is created to store the tweet texts. This DataFrame is then saved as a CSV file named **tweets_with_sentiment.csv** for easy access and further analysis.

## label.ipynb

After rettreiving the tweets from Twitter, now they can be classified by hand. After loading the tweets file, an interactive widget is made to streamline the labeling process. Tweets that display positive sentiment are labeled as 4, neutral sentiment as 0, and negative sentiment as -4. After all tweets in the .csv are labeled, a new .csv titled **combined_tweets_with_sentiment_labeled.csv** is created that contains both the text in the tweet, as well as the sentiment classification.

## new data classifying large.ipynb

The goal of this is to train a reasonably accurate sentiment analysis off of a very large dataset.

First, the dataset of [1.6 million tweets](https://www.kaggle.com/datasets/kazanova/sentiment140) is formatted into a data frame. URls and @s are removed, the strings are stemmed, and then tokenized to be fed into the model as both training and testing data.
> For when I trained the model, I used a 90% training and 10% testing split


## new_Data classifying small.ipynb

