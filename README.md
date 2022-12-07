
# Project: Data Modeling with Postgres

## Table of content

- Introduction
- Technology
- How to run the pipeline
- File structure
- Database schema design
- ETL process
- Maintainers


## Introduction

Startup Sparkify has its new music streaming app running for months. In order to provides better user experience to challenge the existing competitor Sportify, the analytics team is particularly interested in understanding what songs users are listening to. This project is aiming to build a databased which provides solid data stream for the analytical team.


## Technology

- Python 3.8
- psycopg2 2.9.5
- pandas 1.3.4

## How to run the pipeline

1. Launch a brand new Terminal
2. run python create_tables.py to create all tables 
3. run python etl.py to conduct the ETL tasks
4. Open the test.ipynb file through Jupyter notebook to have a overview of the ETL result (Optional)


## File structure

- Assets folder contains all relevant pictures, images, video and other materials used in the project
- data folder stores all music and play logs files in JSON formate. Music files are partitioned by the first three letters of each song's track ID. Log files are partitioned by year and month
- test.ipynb displays the first few rows of each table to let you check your database
- create_tables.py drops and creates your tables
- etl.ipynb reads and processes a single file from song_data and log_data and loads the data into your tables
- etl.py reads and processes files from song_data and log_data and loads them into your tables
- sql_queries.py contains all your sql queries
- README.md provides discussion on your project


## Database schema design

The schema has one measure table songplays and four dimension table time, user, songs and artists. Please see the ERD below to check the details.

![ERD](/assets/ERD.jpeg "ERD")


## ETL process

1. Walking through the song data file and collect all files 
2. Extracting song data and transferring them into DataFrame
3. Inserting song_id, title, artist_id, year and duration data into song table
4. Inserting artist_id, artist_name, artist_location, artist_latitude and artist_longitude data into artist table
5. Extracting log data and transferring them into DataFrame
6. Transforming the timestample into datetime and fetch its year, week of year, month and year part
7. Inserting all the time related data into time table
8. Inserting userId, firstName, lastName, gender, level into user table
9. Joining song table and artist table to get song_id and artist_id
10. Inserting id, tiemstamp, userId, level, songid, artistid, sessionId, location, userAgent


## Maintainer

Allen Chen
email: chenhm03@gmail.com








