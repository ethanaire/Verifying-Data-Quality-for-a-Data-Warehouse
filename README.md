# Hands-on Lab: Verifying Data Quality for a Data Warehouse

Source: Designing, Modeling, and Implementing Data Warehouses Module - Data Warehouses Fundamentals Course by IBM 
Enviroment: Skills Network Cloud IDE (based on Theia and Docker)

## Purpose of the Lab: 
The primary purpose of this lab is to instruct participants on the process of conducting thorough data quality checks in a data warehousing environment. It focuses on using a Python-based framework within a PostgreSQL database to validate data integrity. Key areas of emphasis include identifying null values, duplicates, and invalid entries, as well as verifying data ranges. The lab aims to equip learners with the necessary skills to set up and utilize a testing framework for data validation, ensuring data accuracy and consistency. 

## Objectives: 
- Check Null values
- Check Duplicate values
- Check Min Max
- Check Invalid values
- Generate a report on data quality

## Instructions: 
1. Run the setup script
    ```
    bash setup_staging_area.sh
    ```
    
2. Get the testing framework ready
  2.1. Download the framework
  Run the commands below to download the framework:
   ```
    wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Verifying%20Data%20Quality%20for%20a%20Data%20Warehouse/dataqualitychecks.py

    wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Verifying%20Data%20Quality%20for%20a%20Data%20Warehouse/dbconnect.py

    wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Verifying%20Data%20Quality%20for%20a%20Data%20Warehouse/mytests.py

    wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0260EN-SkillsNetwork/labs/Verifying%20Data%20Quality%20for%20a%20Data%20Warehouse/generate-data-quality-report.py

    ls
    ```
  2.2. Install the python driver for PostgreSQL
  Run the command below to install the python driver for Postgresql database:
    ```
    python3 -m pip install psycopg2
    ```
  2.3. Test database connectivity
  Now we need to check
  - if the Postgresql python driver is installed properly.
  - if Postgresql server is up and running.
  - if our micro framework can connect to the database.
    
  The command below to check all the above cases.
    ```
    python3 dbconnect.py 
    ```
  If all goes well, you should a message `Successfully connected to database`.

  The command also disconnects from the server with a message `Connection closed`.
  
3. Create a sample data quality report 
Run the command below to install pandas:
  ```
  python3 -m pip install pandas tabulate
  ```
Run the command below to generate a sample data quality report: 
  ```
  python3 generate-data-quality-report.py
  ```
You should see a list of tests that were run and their status:
 ![image](https://github.com/ethanaire/Verifying-Data-Quality-for-a-Data-Warehouse-Lab/assets/88173327/b86986f8-9e7c-458a-9d73-26f9db435548)



















