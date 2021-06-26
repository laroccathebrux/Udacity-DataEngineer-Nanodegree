### Sparkify - Data Modeling with Postgres ###

First project from the Udacity Data Engineer nanodegree ***Data Modeling with Postgres***

#### Introduction ###

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Your role is to create a database schema and ETL pipeline for this analysis. You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

#### Strategy ####
![ERD Model](Capturar.PNG)

#### How to execute files ####
- Create the tables with correct relations in sql_queries.py
- run create_tables.py to create tables in database
- program data using etl.ipynb
- test data using test.ipynb
- after all tests done, run again create_tables.py to drop all tables and run etl.py

#### Files in this repo ####
- create_tables.py
    - This files has all functions to create and drop tables in the project
- sql_queries.py
    - Has the database code - (create, insert, select and drop)
- test.ipynb
    - Is a Jupyter Notebook to check the data inserted in every table from the database
- etl.ipynb
    - Is the Jupyter Notebook where all the logical is made for one register in the data files
- etl.py
    - The final code. Where all the data are commited to database
    
#### Examples Queries ####

`SELECT 
    s.song_id, 
    s.artist_id 
FROM songs AS s 
JOIN artists as a ON a.artist_id = s.artist_id 
WHERE s.title = %s 
AND a.name = %s 
AND s.duration = %s`