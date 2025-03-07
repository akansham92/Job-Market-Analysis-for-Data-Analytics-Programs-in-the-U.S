# Job-Market-Analysis-for-Data-Analytics-Programs-in-the-U.S

Background
The field of data analytics is evolving rapidly. According to the Bureau of Labor Statistics, employment in the data domain is projected to grow by 35% from 2024 to 2032—significantly faster than the average for all occupations. 

Despite this growth, job seekers often struggle to align their skills, education, and experience with the evolving market demands, leading to missed opportunities and unfulfilled potential.

Motive:
This project is motivated by the need to address these challenges through data-driven insights and predictive modeling. By analyzing job market trends, skill demands, education levels, and salary distributions, this project aims to provide actionable guidance for:
Identifying the most in-demand roles and high-paying skills.
Aligning education and skill development with current market needs.
Setting realistic salary expectations based on location, experience, and qualifications.

## Data Pre-Processing Steps

Data Integration: 
Combine job posting data from five SERP API extractions (September to November) into one CSV file

Data Cleaning: 
Remove duplicate job postings

Data Formatting:
Standardize location format to "city, state" using regex
Convert Description and Job Highlights to lowercase for feature extraction

## Feature Engineering

Feature Extraction:

Extract job position and job level from the title using keyword matching
Split location into city and state
Use regex and synonym mapping to extract important features like programming languages, visualization tools, databases and big data tools, ml libraries, cloud services, education, experience, soft skills, responsibilities, industries, domains, work modes, and benefits. Impute missing values based on sub-classes
Extract salary information using an NLP question-answering model. Split ranges into min salary and max salary, convert hourly/monthly salaries to annual format, handle outliers manually, and impute missing values based on state, job position, and job level.

Feature Transformation:
numerical features —— StandardScaler
categorical features ——One-Hot 

## Salary Prediction Modelling
Multi-Output Regression Model:
MultiOutputRegressor
RandomForestRegressor

## Technical issues and solution:
Issue: The salary formats are inconsistent, with many extraction and input errors.
Solution: Convert hourly and monthly salaries to annual salaries and Manually identify and correct irregular values and outliers.
Issue: predict min and max salary simultaneously
Solution: Use MultiOutputRegressor

The uniqueness of project:
 Predicts two salary values (min_salary and max_salary) to reflect range-based salary formats.
Provides real-time insights on skills, education, and experience requirements.

Creative idea or feature engineering method:
Since many of our features are Multi-Label Data and the course does not cover Multi-Label Binarization, we used MultiLabelBinarizer to implement One-Hot Encoding. Its output format is identical to traditional One-Hot Encoding.

