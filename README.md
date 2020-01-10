# Wrangle-and-Analyze-Data
This repo contains all the material of 'Wrangle and Analyze Data' practice as part of Udacity's Data Analyst Nanodegree.

## Introduction
The project main objective is to practice the recently developed data wrangling skills, focusing on
fixing the data quality and tidiness issues using Python.

## Data Gathering
1. “Twitter Archive”: The WeRateDogs Twitter archive contained basic tweet data for all 5000+
of their tweets, but not everything. It was “Enhanced” by the addition of the columns rating,
dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo). The dataframe was
previously filtered by ratings only and they were only 2356 at the end.
2. “Tweet Data”: Using the “Tweet_id” from the “Twitter Archive” dataframe of “We Rate
Dogs”, we created a dataframe by querying the Twitter API for each JSON data using
Python’s Tweepy Library.
3. “Image Predictions: The file “image_predictions.tsv” from Udacity’s neural network is
hosted in their own servers and was downloaded programmatically using the requests
library and the provided url.

## Data Assessing
We inspected the data both visually and programmatically in order to find quality and
tidiness issues.

### Quality Issues
DF table:
1. Eliminate retweets (duplicates).
2. "tweet_id" column: is a string not an integer. There are 166 missing values.
3. "in_reply_to_status_id", "in_reply_to_user_id", "retweeted_status_id",
"in_reply_to_user_id", "retweeted_status_id", "retweeted_status_user_id",
"retweeted_status_timestamp" columns: have a lot of missing values. Columns are
unnecesary for this study.
4. "timestamp": is a string instead of time data type.
5. "name" column: has several determiner values as "names"
6. "source" column: has unnecessary html tags instead of utility name e.g. <a
href=""http://twitter.com/download/iphone"" rel=""nofollow"">Twitter for iPhone
7. "rating_denominator" column: has some numbers larger than 10.
Image_predf table:
1. Columns "p1", "p2", "p3": have categories on both lower case and letter case. Names of
columns are not descriptive.
"tweet_data" table:
1. There are duplicated elements with the same "tweet_id" in this table.
2. Change the name of "id" to "tweet_id" like the other tables.

### Tidiness Issues
DF table:
1. "doggo", "floofer", "pupper", "puppo" columns: should be in one column called
"category".
Image_predf table:
1. "breed" column: should be added to df dataframe, using the values of p1_conf and
p1_dog columns on image_predf (image predictions) table
"tweet_data" table:
1. Melt information with df table

## Cleaning
This is the third step of data wrangling process, where above quality and tidiness issues were fixed.
