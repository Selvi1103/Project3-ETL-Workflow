# Project3-ETL-Workflow
## Introduction:
    The Extract, Transform, Load (ETL) process is essential for data engineers, enabling them to manage data from various formats and transform it for further use. In this project, we will demonstrate how to extract data from CSV, JSON, and XML formats, transform it, and load the transformed data into a structured format for further processing. we will:
    Use AWS S3 for storage and retrieval of raw and transformed data.
    Use AWS RDS (Relational Database Service) to load transformed data for further use.
    Optionally use AWS Glue to automate parts of the ETL process, such as schema inference and transformation.


## Objectives:

  By the end of this project, you will be able to:
  Extract data from CSV, JSON, and XML files.
  Transform the extracted data into a desired format, including unit conversions.
  Load the transformed data into a CSV file for future use in databases.
  Log the progress of ETL operations for monitoring purposes.

## Dataset :
  Attached in the repository

## Steps:

**Step 1: Gather Data Files**

**Step 2: AWS Setup**
    
  1. Create an S3 Bucket- use this bucket to store raw data files (CSV, JSON, XML) and the transformed CSV file.
  2. Set Up AWS RDS
  3. Create an RDS instance (MySQL/PostgreSQL) to store the transformed data.
  4. Configure the security groups to allow access from your local machine or AWS Lambda functions.

**Step 3: Import Libraries and Set Paths**
  1. Import necessary libraries like:
  2. glob to handle file formats.
  3. pandas to read CSV and JSON files.
  4. xml.etree.ElementTree to parse XML data.
  5. boto3 for interacting with AWS S3 and RDS.
  6. sqlalchemy for interacting with RDS databases.
  7. datetime to track the progress of each phase through logging.
  8. Install the pandas library .
  9. Set up paths for:
  8. etllog.log file to record the logs.
  10.transformed_data.csv to save the final output.
  11.Set up the AWS credentials and connection details in your environment variables or AWS config files for secure access to S3 and RDS.


**Step 4: Define functions for each step of  ETL**
  1. Extract Data
  2. Transform Data
          The transformation process involves converting: 
          Heights from inches to meters. 
          Weights from pounds to kilograms. 
  3. Load Data
     Load to RDS and S3:After the data is transformed, store the resulting CSV file in the new S3 bucket with the name of transformed_data.
     Load to RDS:Connect to your RDS instance using sqlalchemy and pandas and load the data into a relational database table.
  5. Logging

**Step 5: ETL Execution**
The ETL process follows this sequence: 
1. **Upload Raw Data to S3:**
  Extract raw files from the ZIP and upload them to the S3 bucket.
2. **Extract and Transform Data:**
  Download raw data files from S3, apply transformations, and save the results locally or directly to S3.
3. **Load Data into AWS Services:**
  Upload the transformed CSV back to S3.Load the final transformed data into AWS RDS using SQLAlchemy.Also ensure RDS service will be accessible from your     SQL workbench
4. **Monitor Logs:**
  Ensure that the entire pipeline is logged, and store logs either locally or in S3.

## Conclusion:
  By integrating AWS services like S3, RDS, and Glue, this project simulates a more realistic cloud-based ETL workflow. Data engineers can benefit from cloud storage and databases for better scalability and monitoring of ETL processes. Additionally, logging ensures full traceability, making it easier to debug and audit the pipeline.
