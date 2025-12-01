📦 ETL Pipeline Project — CSV, JSON, XML to SQLite/CSV
Introduction

The Extract, Transform, Load (ETL) process is a core data engineering workflow that enables processing and unifying data from multiple formats.
This project demonstrates how to extract data from CSV, JSON, and XML files, transform it (including unit conversions), and load it into a structured format (CSV file and SQLite database) for further analysis.

Objectives

By completing this project, you will be able to:

Extract data from multiple file formats (CSV, JSON, XML)

Transform the extracted data (e.g., convert height from inches to meters, weight from pounds to kilograms)

Load the transformed data into a CSV file and a SQLite database

Log each ETL phase for monitoring and traceability

Dataset

The dataset contains CSV, JSON, and XML files representing user or record information.

Download the dataset:

wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0221EN-SkillsNetwork/labs/module%206/Lab%20-%20Extract%20Transform%20Load/data/source.zip
unzip source.zip -d ./unzipped_folder


After extraction, the folder contains multiple files, e.g., source1.csv, source1.json, source1.xml, etc.

ETL Steps
1. Extract

CSV files are read using pandas.read_csv()

JSON files are handled line-by-line to support NDJSON or multiple JSON objects per file

XML files are parsed using xml.etree.ElementTree

All extracted data is combined into a single DataFrame

2. Transform

Columns are cleaned (lowercase, stripped)

Heights are converted: inches → meters

Weights are converted: pounds → kilograms

Numeric columns are automatically converted where possible

3. Load

Transformed data is written to:

final_output.csv

etl_output.db SQLite database

SQLite table: people

4. Logging

Each ETL phase (Extraction, Transformation, Loading) is logged

Logs are saved in etl_log.txt for monitoring and debugging

Project Folder Structure
ETL-Project/
│
├── downloads/           # Downloaded CSV, JSON, XML files
├── final_output.csv     # Final transformed CSV
├── etl_output.db        # SQLite database
├── etl_log.txt          # Logs of ETL process
├── etl_pipeline.py      # Main ETL script
└── README.md

How to Run

Clone or download this repository.

Make sure Python 3.x is installed along with pandas.

Run the ETL pipeline:

python etl_pipeline.py


After execution:

final_output.csv contains cleaned and transformed data

etl_output.db contains the same data in SQLite format

ETL Workflow Diagram
+--------------------+      +-------------------+      +---------------------+
|  CSV / JSON / XML  | ---> |  Extract (DataFrame)| ---> | Transform (Units) |
+--------------------+      +-------------------+      +---------------------+
                                                                  |
                                                                  v
                                                         +---------------------+
                                                         |      Load          |
                                                         | CSV + SQLite DB    |
                                                         +---------------------+

Conclusion

This project demonstrates a complete ETL workflow in Python:

Extracting data from multiple formats

Transforming it into standardized units

Loading it into structured storage

Logging each step for monitoring

It showcases practical data engineering skills, including handling multiple file types, cleaning, transforming, and preparing datasets for downstream applications.
