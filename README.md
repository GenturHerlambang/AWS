# AWS Data Engineer Project - End-to-End Data Pipeline



This repository contains a simple end-to-end data engineer project using AWS services. The project involves setting up a data pipeline to process data from the YouTube New dataset sourced from Kaggle. The data pipeline is designed to handle data ingestion, processing, storage, and analysis in AWS.

# Dataset
The data for this project is gathered from the YouTube New dataset on Kaggle. It consists of various attributes related to YouTube videos, including views, likes, dislikes, and comments.

# Project Structure
- youtubecoba-raw-s3: Contains AWS CLI commands to copy the raw data files to an S3 bucket.

- youtubecoba-lambda: Includes an AWS Lambda function code to process the raw JSON data and write the processed data as Parquet format to another S3 layer.

- youtubecoba-clean-parq-rev2: Contains the Glue ETL script to further process the data and write it as Parquet format to a different S3 location with partitions based on the region.

# Data Pipeline Steps

- Data Ingestion: The raw data files (CSVs) are fetched from Kaggle and copied to the designated S3 bucket using AWS CLI commands.

- Data Processing (Lambda): The AWS Lambda function (youtubecoba-lambda) processes the raw JSON data, normalizes it, and extracts the required columns. The processed data is written as Parquet format to a designated S3 layer.

- Data Processing (Glue ETL): The Glue ETL script (youtubecoba-clean-parq-rev2) reads the data from the S3 layer created by the Lambda function. It applies mapping transformations, filters the data based on specified regions (ca, gb, us), and writes the processed data as Parquet format to a different S3 location with partitions based on the region.

# AWS Services Used

Amazon S3: Data storage and retrieval.

AWS Lambda: Serverless compute service for processing data in response to events.

AWS Glue: Fully managed ETL (Extract, Transform, Load) service for data processing.
Note

# Visualization
for an exampe of the finish vsiualuzation data can be seen here:
https://ap-southeast-1.quicksight.aws.amazon.com/sn/dashboards/96445539-bbf9-47ed-a4e3-6f2c746ac6cb

For detailed execution and setup instructions, please refer to the individual files (youtubecoba-raw-s3, youtubecoba-lambda, and youtubecoba-clean-parq-rev2). Ensure proper configuration of AWS credentials, S3 buckets, Glue database, and tables before running the data pipeline.
