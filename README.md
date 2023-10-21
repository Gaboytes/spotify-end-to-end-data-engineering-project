# Spotify End-to-End Data Engineering project
 

 ### Architecture
 ![Architecture](https://github.com/Gaboytes/spotify-end-to-end-data-engineering-project/blob/main/pictures/spotify%20imagen.jpg)

### Introduction 
In this project I built an ETL(Extract, Transform, Load) pipeline using the Spotify API on AWS. The pipeline will retrieve data from the Spotify API, transform it to a desired format, and load it into an AWS data store.
- Getting the data from Spotify API about Top 50 global songs because we want to know what is ringing in the world in a daily basis (songs , albums and artists)

 ![spotify](https://github.com/Gaboytes/spotify-end-to-end-data-engineering-project/blob/main/pictures/top%2050%20.png)

- For this project we are gonna apply ETL process to deploy our project to the cloud 
 
![etl](https://github.com/Gaboytes/spotify-end-to-end-data-engineering-project/blob/main/pictures/etl.png)

### About Dataset/API
This API contains information about music artists, albums, and songs - [Spotify API](https://developer.spotify.com/documentation/web-api)

 ### Services Used
1. **S3 (Simples Storage Service):** Amazon S3 (Simply Storage Service) is a highly scalable object storage service that can store and retrieve any amount of data from anywhere on the web. It is commonly used to store and distribute large media files, data backups, and static website files

2. **AWS Lambda:** AWS Lambda is a serverless computing service that lets you run your code without managing servers. You can use Lambda to run code in response to events like changes in S3, DynamoDB, or other AWS services.

3. **Cloud Watch:** Amazon Cloudwatch is a monitoring service for AWS resources and the applications you run on them. You can use Cloudwatch to collect and track metrics, collect and monitor log files, and set alarms.

4. **Glue Crawler:** AWS Glue Crawler is a fully managed service that automatically crawls your data sources, identifies data formats, and infers schemas to create an AWS Glue Data Catalog.

5. **Data Catalog** AWS Glue Catalog is a fully managed metadata repository that makes it easy to discover and manage data in AWS you can use the Glue Data Catalog with other AWS services, such as Athena.

6. **Amazon Athena:** Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 Using standard SQL. You can use Athena to analyze data in your Glue Data Catalog or in other S3 buckets.

### Install Packages
```
pip install pandas
pip install numpy
pip install spotipy
```

### Project Execution Flow 
Extract Data from API -> Lambda Trigger (Every day) -> Run Extract Code -> Store Raw Data -> Trigger Transform Function -> Transform Data and Load IT -> Query Using Athena 

The entire data pipeline is designed to be automated and scheduled to run daily. The AWS Lambda Function responsible for data extraction is triggered by Cloud Watch on a daily basis. This ensures that the latest data from the Spotify API is fetched regularly.

Upon successful extraction, the transformation process is triggered automatically for the newly uploaded data. The transformed data is then moved to their respective folders, and the raw data is removed to keep the data clean and organized.

Finally, the data is loaded into Amazon Athena Data Warehouse, providing a centralized and scalable database for performing data analytics and generating insights.

Optionally the data can be exported to any visualization tool in order to create dashboards or EDA looking for new insights and conclusions.


### Exploratory Data Analysis 

Check the Jupyter Notebook --->  [Analysis](https://github.com/Gaboytes/spotify-end-to-end-data-engineering-project/blob/main/Spotify%20Data%20Eng%20Pipeline%20Project%20.ipynb)


### Dashboard
![image](https://github.com/Gaboytes/spotify-end-to-end-data-engineering-project/assets/145523136/eb7f2f97-57a6-4945-b2ec-30ae60d28b60)

- Live Dashboard = [Link](https://www.novypro.com/project/spotify-dashboard-power-bi-1)


### Tech Used
To make this I started with a Kaggle [dataset](https://www.kaggle.com/datasets/nelgiriyewithana/top-spotify-songs-2023) :
- Enriched the dataset using ChatGPT Code generation
- Python to call Spotify's Web API to get images
- Powerpoint for the Glassmorphism layout
- HTML visuals for the Cover Art
- DENEB Heatmap with bars
- DENEB Unit charts
- Heatmap code here = 🔗 https://github.com/PowerBI-tips/Deneb-Templates/blob/main/templates/heatmap%20with%20bars%20-%20red%20themed.json
- Unit chart code here (from Davide Bacci) = 🔗  https://github.com/PBI-David/Deneb-Showcase

### Conclusions
By implementing this fully automated data pipeline, we ensure that new data from the Spotify API is efficiently processed and made available for analysis. This project showcases the power and versatility of AWS Cloud Platform in building robust and automated data engineering solutions.


