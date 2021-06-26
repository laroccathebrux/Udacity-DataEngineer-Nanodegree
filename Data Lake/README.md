# Data Lake #

## Introduction ##

A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

As their data engineer, you are tasked with building an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.

You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

## Project Description ##

In this project, you'll apply what you've learned on Spark and data lakes to build an ETL pipeline for a data lake hosted on S3. To complete the project, you will need to load data from S3, process the data into analytics tables using Spark, and load them back into S3. You'll deploy this Spark process on a cluster using AWS.

### Fact Table ###
**songplays** - records in event data associated with song plays i.e. records with page NextSong

### Dimension Tables ###
**users** - users in the app
**songs** - songs in music database
**artists** - artists in music database
**time** - timestamps of records in songplays broken down into specific units

## Spark Process ##
The ETL job processes the song files then the log files. The song files are listed and iterated over entering relevant information in the artists and the song folders in parquet. The log files are filtered by the NextSong action. The subsequent dataset is then processed to extract the date, time, year etc. fields and records are then appropriately entered into the time, users and songplays folders in parquet for analysis.

## Project Structure ##
**etl.py** - The ETL to reads data from S3, processes that data using Spark, and writes them to a new S3
**dl.cfg** - Configuration file that contains info about AWS credentials