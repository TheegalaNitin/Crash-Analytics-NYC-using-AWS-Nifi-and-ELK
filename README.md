# Crash Analytics on New York City Open Data using Tools of AWS, Apache Nifi and ELK(Elasticsearch Logstash Kibana) Framework

## Introduction
This project explores NYC crash data analytics using modern data engineering practices on AWS. It demonstrates how to build a scalable, production-oriented data pipeline that automates data ingestion, transformation, storage, and visualization.

The pipeline leverages Apache NiFi for ETL orchestration, Amazon S3 for data lake storage, Amazon EMR (with Logstash) for processing, and Amazon OpenSearch + Kibana for real-time analytics and visualization.

The goal is to transform raw API data into analytics-ready datasets and generate actionable insights through interactive dashboards.

## Architecture
![Project Architecture](https://github.com/TheegalaNitin/Crash-Analytics-NYC-using-AWS-Nifi-and-ELK/blob/main/Architecture%20of%20NYC.png)

## Technology Used
1. Programming & Query Languages
- Python
- SQL
2. Cloud Platform – AWS
- Amazon EC2 (NiFi Deployment)
- Amazon S3 
- Amazon EMR 
Amazon OpenSearch (Search & Analytics Engine)
3. Data Engineering Tools
- Apache NiFi (Data Ingestion & ETL)
- Apache Spark (via EMR – optional processing layer)
- Logstash (Data Pipeline to OpenSearch)
- Kibana (Visualization & Dashboarding)


## Dataset Used
NYC Motor Vehicle Collisions Dataset

https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data

This dataset contains detailed crash records including:

- Crash date and time
- Location (borough, zip, latitude, longitude)
- Contributing factors
- Vehicle types
- Injury and fatality counts
- Weather conditions

## Data Pipeline (ETL Flow)
- Extract – Apache NiFi
 * Uses InvokeHTTP to fetch data from NYC Open Data API
 * Continuously ingests real-time crash data
- Transform – Apache NiFi
 * EvaluateJSONPath → Extract relevant attributes
 * ReplaceText → Convert JSON → CSV
 * MergeContent → Combine records into structured datasets
- Load – Amazon S3
 * Processed CSV files stored in S3
 * Acts as a scalable data lake

## Scripts for project
1. [Extract Python File](mage-files/extract.py)
2. [Load Python File](mage-files/load.py)
3. [Transform Python File](mage-files/transform.py)


## Complete Video Tutorial
Video Link - https://www.youtube.com/watch?v=WpQECq5Hx9g

