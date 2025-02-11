# ETL Telecom Project with SSIS 
This project demonstrates how to implement an ETL process for a telecom company using SQL Server Integration Services (SSIS). The goal was to automate the storage and transformation of customer transaction data received periodically in CSV files.
## Project Details
The telecom company generates a CSV file every 5 minutes, containing transaction data such as customer movement records. This project focuses on processing the CSV data, applying transformation rules, validating the data, and storing it in a database while handling rejected records.
## Key Features
#### Data Transformation
   The raw transaction data is validated and transformed using a series of business rules. For example, IMSI and IMEI fields are validated and formatted, and incorrect or incomplete records are rejected.
####	Validation & Mapping
- **ID**: Directly mapped as `Transaction_id`.
- **IMSI**: Validated and rejected if null.
- **IMEI**: Substrings of the IMEI are extracted, with default values assigned if the IMEI is invalid.
- **EVENT_TS**: Timestamp format is validated and rejected if incorrect.
- **Rejected Records**: Invalid records are stored in a separate table, with the original file name logged.

####	Data Storage:
The project stores the transformed data into a relational database and tracks statistics such as the total number of records, the number of records successfully stored, and the number of rejected records.
####	File Management:
   After the ETL process is completed, the original CSV file is moved to a separate folder, keeping the directory organized.
## Technologies Used
- SQL Server Integration Services (SSIS): For data extraction, transformation, and loading.
- SQL Server: For storing the processed data.
## Conclusion
This project showcases an efficient and automated ETL solution for telecom transaction data, ensuring that only clean, validated data is stored, and rejected records are handled separately for further analysis.
