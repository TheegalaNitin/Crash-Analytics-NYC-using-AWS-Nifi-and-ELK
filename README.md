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

## Initialising the EC2 instance and downloading Apache Nifi
![EC2 initialisation and Nifi installation](https://github.com/TheegalaNitin/Crash-Analytics-NYC-using-AWS-Nifi-and-ELK/blob/main/Project%20screenshots%202/Picture1.png)

## Setting up Nifi processors  working in tandem from extracting data from API to putting the parsed objects in S3 bucket
![Apache Nifi processors](https://github.com/TheegalaNitin/Crash-Analytics-NYC-using-AWS-Nifi-and-ELK/blob/main/Project%20screenshots%202/Picture2.png) 

## Visualising the data using Kibana 
![Kibana Visualisation](https://github.com/TheegalaNitin/Crash-Analytics-NYC-using-AWS-Nifi-and-ELK/blob/main/Project%20screenshots%202/Picture3.png)




## Conclusion and Reflection 

This project has helped me understand the different tools available for performing ETL tasks. This was my first time using AWS cloud and tools associated with it. While I have done a lot of experimenting and didn't add many steps that I used. I request the readers to please refer to the repository Project Screenshots 2 (https://github.com/TheegalaNitin/Crash-Analytics-NYC-using-AWS-Nifi-and-ELK/tree/9948dafbc72c232e8f329e98b00bc8679f37f410/Project%20screenshots%202) for more detailed excution of the project. I didn't add them to the readme as it would be very lengthy. 

## Credits:

* I would like to thank Darshil Parmar on explaining how to use Github to showcase projects. The format for readme files is inspired from his work which I forked to suit my project. I would request readers to please support his work. https://youtube.com/@darshilparmar?si=T1SL0Di8-SH029zb

