# Covid-19_Project
Create an ETL pipeline in AWS using S3, Redshift and Glue

This is a data engineering project where I worked on Covid-19 dataset. This project is performed on AWS. You can download dataset from ![google drive](https://drive.google.com/drive/folders/18PlEVh2IpFYCbORhDBgQ09llG_n9aO3n).

![Project overview](https://user-images.githubusercontent.com/82932314/209496778-052c3a4e-89e9-44ae-87e4-54d8c5502ed5.PNG)

I used the boto3 library to interact with AWS using Python.

In the first step, I created a function to extract data from S3 and convert it to a Python dataframe using Athena. This fuction is little complicated so you may get in 
touch with me to undertand more about it.

I converted these data into facts and dimensions and saved them to the S3 bucket. For this, I used the StringIO function of the io library. 

![Dimension](https://user-images.githubusercontent.com/82932314/209495647-4b5911ad-111d-42ff-85fb-461b7205f6dd.jpg)

Then I created a cluster my-first-redshift in Redshift using the Boto3 library. I gave specifications like DB name, username, password, etc. Apart from Boto3, you can also use the library redshift_connector to connect with Redshift. It works similarly to Boto3 and you need to mention your hostname, DB, username, and password and the connection will be established. Then I created fact and dim tables using the cursor function. Now we are ready to copy data from S3 to Redshift, which is a copy-paste job. Using copy command you can copy data from S3 to Redshift and make sure that you are moving data in the same region. Here I created an S3 bucket shiv-data-engineering-covid and Redshift DB myfristdb in the Mumbai region.
