# Description

This repository contains the ETL pipeline for populating the sparkifydb database.

    -   The goal of this database is to allow Sparkify to answer business questions about its users, the types of songs they listen to, and the artists who write those songs, using data from logs and files. The database serves as a consistent and dependable repository for this information.

    -   This data source will be useful in assisting Sparkify in achieving some of its analytical goals, such as identifying songs with the highest popularity or times of day with the highest traffic.    
  
## Database Design and ETL Pipeline
---
* For the schema design, the STAR schema is used as it simplifies queries and provides fast aggregations of data.

![Schema](schema.PNG)

* For the ETL pipeline, Python is used as it contains libraries such as pandas, that simplifies data manipulation. It also allows connection to Postgres Database.

* There are 2 types of data involved, song and log data. For song data, it contains information about songs and artists, which we extract from and load into users and artists dimension tables

* Log data gives the information of each user session. From log data, we extract and load into time, users dimension tables and songplays fact table.

## Running the ETL Pipeline
---
* First, run create_tables.py to create the data tables using the schema design specified. If tables were created previously, they will be dropped and recreated.

* Next, run etl.py to populate the data tables created.