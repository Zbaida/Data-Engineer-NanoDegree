# Udacity Project 4 - Data Lakes

## Introduction
Sparkify's data and user population is growing rapidly and they need to move their data warehouse to a data lake. Currently, their data sits in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

The goal of this project is to build an ETL pipeline that extracts Sparkify's data from S3, processes them using Apache Spark, and loads the data back into AWS S3 as Spark parquet files.


## Schema for Song Play Analysis
Just like in previous projects for this course, we will be creating a star schema optimized for queries on song play analysis.

## ETL (Extract, Transform, Load) Pipeline
1. Load AWS credentials  (dl.cfg)
2. Read Sparkify data from S3
    - song_data: s3://udacity-dend/song_data
    - log_data: s3://udacity-dend/log_data
3. Process the data using Apache Spark.
    - Transform the data and create five tables (see 'Tables' above)
4. Load data back into S3

## S3 Buckets
- Bucket 1 (song_data): s3://udacity-dend/song_data 
    - contains static data about artists and songs
- Bucket 2 (log_data): s3://udacity-dend/log_data 
    - contains user data (who listened what song, when, where, etc)

### Tables
- **Fact Table:** songplays: attributes referencing to the dimension tables
- **Dimension Tables:** users, songs, artists and time table

## How to run ETL process
Here is how to run this project on the Udacity local mode:
1. Update 'dl.cfg' file with your AWS credentials
> AWS_ACCESS_KEY_ID     = YOUR_AWS_ACCESS_KEY_ID
> AWS_SECRET_ACCESS_KEY = YOUR_AWS_SECRET_ACCESS_KEY
> INPUT_DATA            = s3://<YOUR_BUCKET_NAME>/
> OUTPUT_DATA           = s3://<YOUR_BUCKET_NAME>/output_data/
> INPUT_DATA_SD         = s3://<YOUR_BUCKET_NAME>/song_data/*/*/*/*.json
> INPUT_DATA_LD         = s3://<YOUR_BUCKET_NAME>/log_data/*/*/*.json



    
