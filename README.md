# NYC Yellow Taxi Databricks Pipeline (Bronze → Silver → Gold)

## Introduction
The goal of this project is to perform  optimization on NYC Yellow Taxi data using various tools and technologies, including Databricks, Python, Databricks Notebooks, PySpark, Spark SQL, and Delta Lake. An end-to-end ETL pipeline built on ** Databricks (free edition)** using **PySpark** and **Delta Lake**.  
This project demonstrates how to ingest raw NYC taxi trip data, clean and transform it, and optimize query performance using Delta features like `OPTIMIZE`.


## Architecture

<img src="architecture.jpg">


## Technology Used
Programming Language - Python
Databricks ( Free Edition )
PySpark
Spark SQL


## Dataset Used
TLC Trip Record Data Yellow and green taxi trip records include fields capturing pick-up and drop-off dates/times, pick-up and drop-off locations, trip distances, itemized fares, rate types, payment types, and driver-reported passenger counts.

Here is the dataset used in the project - https://github.com/Utt0018/databricks-nyc-taxi/blob/main/data/yellow_taxi.parquet

More info about the dataset can be found here: 

Website - https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

## Analytics and Optimization Output on Gold Table

+---------------+------------------------------------------------+------------------+---------+---------+-------------+--------------------+------------------+----------------------+------------------+
|Stage          |cat_counts                                      |distinct_loc_pairs|num_files|row_count|size_in_bytes|time_cat_groupby_sec|time_count_sec    |time_distincts_loc_sec|total_time_sec    |
+---------------+------------------------------------------------+------------------+---------+---------+-------------+--------------------+------------------+----------------------+------------------+
|Before OPTIMIZE|{Short -> 40617, Medium -> 67353, Long -> 82642}|23576             |1        |190612   |517346       |0.5308501720428467  |0.5132696628570557|0.5394151210784912    |1.9198203086853027|
|After OPTIMIZE |{Short -> 40617, Medium -> 67353, Long -> 82642}|23576             |1        |190612   |517346       |0.49340200424194336 |0.3314552307128906|0.46826910972595215   |1.6394078731536865|
+---------------+------------------------------------------------+------------------+---------+---------+-------------+--------------------+------------------+----------------------+------------------+

