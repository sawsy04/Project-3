# Project 3: Subreddit Classification

## Problem Statement

Reddit receives numerous posts on a daily basis and it is crucial that Reddit successfully identifies the correct category of those posts. This increases user engagement as it allows more users to share their knowledge. While there may be people who can categorize these post into their relevant subreddits, it may be increasingly challenging to do so manually with more and more posts. 

In this project, we will be developing classification models that can distinguish which of two subreddits,([r/nosleep](https://www.reddit.com/r/nosleep/) or [r/AsianBeauty](https://www.reddit.com/r/AsianBeauty/)) the post belongs to as accurately as possible. We will compare two classification models- (i) Logistic Regression and (ii) Multinomial Naive Bayes. We will evaluate the model using accuracy score, as well as looking at the recall and precision of the model.

## Overview

1.  Web Scrapping Notebook: Using Reddit's API, we'll be collecting posts from two subreddit - nosleep and AsianBeauty.
2. Data Cleaning, Preprocessing and Modelling Notebook: Subsequently, we'll use NLP to train the classifier on which subreddit a given post came from.

## Methodology

To get Reddit's post, all we have to do is to add `.json()` to the end of the url and we'll be able to scrap the posts to get what we want. 

### Data Dictionary of the data scrapped from Reddit

|Feature|Type|Description|
|---|---|---|
|subreddit|object|Shows us which subreddit does the post belong to - No sleep or Asian Beauty|
|title|object|The title of the post|
|content|object|The content of the post|
|name|object|The name of the person who posted the post|
|nosleep|int|A flag to show whether the post belong to nosleep subreddit or not|


Before training the model, we would have to clean and pre-process the text that we scrap from Reddit and subsequently vectorize the text. In this project, we would explore gridsearch to optimize hyperparameters across two different kind of vectorizers (CountVectorizer and TfidfVectorizer) as well as classification estimators (Logistic Regression and Multinomial Naive Bayes) to find the best classification model that can assist us in classifying posts as accurately as possible.


## Findings

In this scenario, false negative and false positive are equally bad as they mean misclassification of the post. So, we would choose the best model based on the highest accuracy score. Using GridSearch, the vectorizer and estimator with the best accuracy score (score:1.0) is CountVectorizer with Logistic Regression. 

## Future work

To consider classifying posts from other subreddits that are slightly more similiar in nature so see if the model really works as well.


