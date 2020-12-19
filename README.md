OVERVIEW:
    Using machine learning, we will project occupational growth/decline in the next 10 years in California. 

    Which occupation will be highest in demand in California in the next 10 years?

DATA SOURCES WE USE:
•	https://data.edd.ca.gov/Industry-Information-/Current-Employment-Statistics-CES-/r4zm-kdcg
Current Employment Statistics (CES)
**USE FOR MACHINE LEARNING**
•	https://data.edd.ca.gov/Wages/Occupational-Employment-Statistics-OES-/pwxn-y2g5
Occupational Survey data 20 years
Occupational_Employment_Statistics__OES_.csv
•	https://data.edd.ca.gov/Wages/Occupational-Employment-Statistics-OES-/pwxn-y2g5
Occupational Survery data 20 years
Occupational_Employment_Statistics__OES_.csv
•	https://data.edd.ca.gov/Labor-Force-and-Unemployment-Rates/Local-Area-Unemployment-Statistics-LAUS-/e6gw-gvii/data
Local_Area_Unemployment_Statistics__LAUS_.csv
•	https://data.edd.ca.gov/Labor-Force-and-Unemployment-Rates/Unemployment-Rate-by-Age-Groups/bcij-5wym
Unemployment_Rate_by_Age_Groups.csv


FEATURES:
    Tableau
    Postgres (AWS)
    
LANGUAGES/INSTALLATONS:  
    HTML/CSS
    Python Pandas
    Python Matplotlib 
    Scikit-Learn

NOTE:
    

STEPS -

1. Copy APIs from EDD files.
2. Import one CSV file on AWS and use the URL in Google Collaboration.
3. In Google Collaboration, clean up data and create dataframes.
4. Create database in pgAdmin and create tables with code at the bottom.
5. After initial setup, server can be created with the following:
server name: "occupation-trends"
HOST: occupation-trends.cppwghmqrqzq.us-west-1.rds.amazonaws.com
username : root
pwd : data1234
6. Access to the Tableau file to view story.

<!-- CREATE USER admin22 with Password '12345'
Alter User admin22 With SuperUser;

IF EXISTS(SELECT *
FROM dbo.occupation-trends)
DROP TABLE dbo.unemployment_rate_by_age
DROP TABLE dbo.local_area_unemployment_stats
DROP TABLE dbo.longterm_occupational_employment
DROP TABLE dbo.occupational_employment_stats
DROP TABLE dbo.current_employment_stats

CREATE TABLE unemployment_rate_by_age(
area_name VARCHAR,
year INT,
age_16_19 FLOAT,
age_20_24 FLOAT,
age_25_34 FLOAT,
age_35_44 FLOAT,
age_45_54 FLOAT,
age_55_64 FLOAT,
age_65 FLOAT
);

CREATE TABLE local_area_unemployment_stats(
area_name VARCHAR,
year INT,
employment INT,
unemployment INT,
unemployment_rate FLOAT
);

CREATE TABLE longterm_occupational_employment(
area_name VARCHAR,
period VARCHAR, 
occupational_title VARCHAR, 
percentage_change FLOAT,
median_hourly_wage FLOAT,
median_annual_wage FLOAT,
entry_level_education VARCHAR
);

CREATE TABLE occupational_employment_stats(
area_name VARCHAR,
year INT,
wage_type VARCHAR,
occupational_title VARCHAR,
mean_wage FLOAT
);

CREATE TABLE current_employment_stats(
area_name VARCHAR,
year INT, 
industry_title VARCHAR,
current_employment INT
);
