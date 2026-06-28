
****************************  ETL Pipeline Automation – Government of India Open Data API   ***********************************

📌 Project Overview

This project demonstrates a complete ETL (Extract–Transform–Load) pipeline automation using Python and Pandas. 
The pipeline connects to the Government of India Open Data API for commodity arrivals, automates data ingestion, applies cleaning and transformation steps, and saves the processed dataset for downstream analysis.

🔹 Dataset Details

•	Source: Government of India Open Data API

•	Columns:
o	Arrival_Date
o	Commodity
o	Commodity_Code
o	District
o	Grade
o	Market
o	Max_Price
o	Min_Price
o	Modal_Price
o	State
o	Variety

•	Coverage: Records from 2009 to 2023
•	Volume: ~1800 records for 2009, ~44 records for 2023, no records for 2024–25
•	Data Quality Issues: Many rows with blank Arrival_Date, sparse coverage for recent years

🔹 ETL Pipeline Design

•	Extract:
o	Automated pagination with API calls (limit and offset).
o	Pulled records in batches to handle large datasets.

•	Transform:
o	Cleaned column names for consistency.

o	Converted Arrival_Date to datetime format.
o	Dropped rows with missing or invalid dates.
o	Applied filters for specific years or date ranges (e.g., Jan–Dec 2023).

•	Load:
o	Exported cleaned dataset to CSV for downstream use.
o	Logged record counts and date ranges for validation.

🔹 Challenges & Resolutions
            Challenge	                                          Resolution
Empty DataFrames when filtering	                  Verified actual column names (Arrival_Date vs arrival_date) and corrected usage.
Datetime conversion errors	                      Applied safe parsing with errors='coerce' and dropped invalid rows.
Sparse coverage for 2023 (only 44 records)	      Confirmed dataset limitation via min/max date checks; documented as a data quality issue.
Missing values in Arrival_Date	                  Dropped blanks before filtering to avoid errors.
No data for 2024–25	                              Verified via range checks; concl  uded dataset is incomplete for those years.
API filter limitations	                          Pulled all records first, then applied local filtering in pandas.

🔹 Outcome
•	Built a fully automated ETL pipeline: Extract → Transform → Load.
•	Implemented robust data cleaning and error handling for missing values.
•	Verified dataset coverage (2009–2023) and documented limitations.
•	Delivered a reusable pipeline template for other datasets.

🔹 Portfolio Value
This project demonstrates:
•	Ability to automate data pipelines with Python.
•	Skill in handling messy, real world datasets.
•	Professional documentation of challenges and resolutions.
•	Adaptability to diagnose data quality issues and communicate them clearly.
