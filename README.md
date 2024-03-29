# YouTube Data Analysis and Data Lake Creation

Introduction:
The YouTube Data Analysis Project efficiently manages, transforms, and analyzes structured and semi-structured YouTube video data. In this project, I Built an ETL(Extract, Transform, Load) pipeline using a static dataset of trending YouTube videos. The pipeline will retrieve data from the dataset, transform it to a desired format(parquet), and load data into s3. After the data has been loaded, a glue crawler will be used to create a glue catalog which will be used later on for analytics using Athena.

Services Used:
• Amazon S3: An object storage service for secure and scalable data storage. 

• AWS IAM: Identity and Access Management for managing secure access to AWS resources. 

• Amazon QuickSight: A serverless business intelligence service for data visualization and analysis. 

• AWS Glue: A serverless data integration service for data discovery, preparation, and combination. 

• AWS Lambda: A compute service for running code without managing servers. 

• AWS Athena: An interactive query service for analyzing data directly in Amazon S3.



Project Execution Flow
Create an S3 Bucket for Raw Data --> Load data using the CLI commands -->Create a Crawler and Crawl Open the Data --> Create Glue Catalog --> Error with the Json Format(Serde) --> Pre-processing the data --> Json-to-parquet-transformation --> Run a crawler again --> query in Athena for analytics --> Create a new DB for the Target --> Crate a new Glue Job(Do necessary transformations such as dropping null fields, and arranging the schema) --> Add a S3 Trigger to Orchestrate --> Create a Glue Job To Join(inner) tables --> Load data to Final Target --> Quicksight for Visualizations




Dataset Used:
The project utilizes a statc dataset that contains daily statistics of popular YouTube videos. The dataset includes CSV files with information such as video title, channel title, publication time, tags, views, likes, dislikes, description, and comment count. Additionally, a JSON file provides category details specific to each region.
LINK: https://www.kaggle.com/datasets/datasnaek/youtube-new


