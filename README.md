# Covid-19_Project
Create an ETL pipeline in AWS using S3, Redshift and Glue

This is a data engineering project where I worked on Covid-19 dataset. This project is performed on AWS. You can download dataset from google drive.

I used boto3 library to interact with AWS using Python.

In the first step I created a function to extract data from S3 and convert to Python dataframe using Athena. This fuction is little complicated so you may get in touch with me to undertand more about it.

I converted these data into fact and dimentions and saved them to S3 bucket. For this I used StringIO fuction of io library. ![Dimension](https://user-images.githubusercontent.com/82932314/209495647-4b5911ad-111d-42ff-85fb-461b7205f6dd.jpg)

Then I created a cluster my-first-redshift in Redshift using Boto3 library. I gave specifications like DB name, username, password etc. Apart from Boto3 you can also use library redshift_connector to connect with Redshift. It works similar to Boto3 and you need to mention hostname, db, username and password and connection will be established. Then I created fact and dim tables using cursor fuction. Now we are ready to copy data from S3 to Redshift and it is as a copy paste job. Using copy command you can copy data from S3 to Redshift and make sure that you are moving data in the same region. Here I created S3 bucket shiv-data-engineering-covid and Redshift DB myfristdb in the region Mumbai.
