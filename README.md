# Data Science Job Postings — Power Query Cleaning & Salary Analysis


## Overview

This project analyzes a dataset of [data-science job postings](https://www.kaggle.com/datasets/rashikrahmanpritom/data-science-job-posting-on-glassdoor?utm_source=chatgpt.com&select=Uncleaned_DS_jobs.csv) from Kaggle, focusing on data cleaning, transformation, and salary insights using Microsoft Excel Power Query.

The cleaned dataset is then used to answer several business questions:

1. Which job titles/position types pay the best?

2. Which U.S. states offer the highest salaries for data roles?

3. Which companies pay the highest salaries?

4. What company sizes offer better compensation?

This project showcases practical skills in Power Query ETL, data cleaning, column transformations, splitting & merging, grouping, and aggregated salary analysis.


## Project Files

- `clean data by power query.xlsx`: Include all project works
    - This file includes seven tables:
    
      1. Uncleaned_DS_jobs.xlsx	Raw dataset imported from Kaggle.
      2. Final_cleaned_DS_jobs.xlsx	Fully cleaned version after Power Query transformations.
      3. Salary by Position Type.xlsx	Summary table showing min & max salary by job category.
      4. Salary by Size.xlsx	Salary comparison by company size groups.
      5. Salary by State.xlsx	Salary ranking by U.S. state.
      6. Salary by Company.xlsx	Aggregated salary calculations for companies.
      7. Salary by Size and Position Type.xlsx	Combined pivot of position type × company size.

- `Uncleaned_DS_jobs.xlsx`
- `state_mapping.xlsx`
- `README.md`


## Data Cleaning Steps (Power Query)

1. **Duplicate Check**

      All rows were checked for duplicates — no duplicates were found.


2. **Salary Estimate Cleaning**

   - The “Salary Estimate” field contained ranges like: 
     `$137K–$171K (Glassdoor est.)`

   - Extracted only the salary range before the "(" bracket.

   - Split into two numeric columns:
        **Min Salary** and **Max Salary**
   
   - Converted values to proper currency format ( currency, then × 1000)
   

 3. **Position Type Standardization**

    The dataset contained many variations of job titles.
    A clean categorical column called **Position Type** was created with 5 groups:

    - Data Scientist
    - Data Analyst
    - Data Engineer
    - Machine Learning
    - Other
    

 4. **Company Size Cleaning**

    In this column, some values included "–1" or "Unknown" → these were removed.

    Final size groups included categories such as:

    - 1 to 50 employees
    - 51 to 200
    - 201 to 500
    - 501 to 1000
    - 1001 to 5000
    - 5001 to 10,000
    - 10,000+ employees
    

5. **Location Parsing (City & State)**

   This column includes the city and state separated by a comma. 
   Some values with inconsistent formats were shown, such as:

   - New Jersey
   - California
   - Patuxent, Anne Arundel, MD
   - Remote
   - Texas
   - Utah
   - United States

   Steps taken:

   - Created a Location Correction column to fix irregular patterns.
   - Split cleaned location into two new columns: **City** and **State Abbreviation**
   - Merged with a reference states table to ensure valid state names.
   - Create and add a new column called **State Fullname**
    

 6. **Company Name Cleaning**

    - Company names contained ratings, e.g.:
        `Pfizer (4.1)', "Meta (3.8)`

    - Renamed original to **Company Name (with rating)**
    - Created new column **Company Name** containing only the clean company name.
    
    

## Analysis Produced

   Power Query aggregation tables answer the project’s questions:
 
   1) Salary by Position Type: Shows which of the five defined roles pay the most (based on mean max salary and mean min salary).
   
  2) Salary by Company Size: Identifies which company size groups offer higher salaries on average.
  
  3) Salary by State: Ranks U.S. states by average minimum and maximum salary.

  4) Salary by Company: Shows the highest-paying employers based on aggregated salary estimates.

  5) Salary by Position Type × Company Size: Cross-tab analysis revealing how job type salary varies by organization size.
  
 


## Tools & Skills Used

- `Microsoft Excel Power Query`

- `Column splitting and merging.`

- `Custom column creation.`

- `Conditional transformations`

- `Text extraction`

- `Filtering and trimming.`

- `Grouping and aggregations`

- `Merging reference tables.`

- `Data Cleaning & Standardization`

- `Data Modeling and Salary Insights`



## Acknowledgments

   This project was completed as part of a self-driven portfolio development exercise to strengthen skills in:

   `Power Query ETL pipelines`
   
   `Excel-based data modeling`
   
   `Salary data analysis`
   
   `Data cleaning best practices`
    
    
## Result

  This analysis shows that Machine Learning and Data Scientist roles offer the highest salary ranges.
Large companies and certain states (such as Delaware and North Carolina) consistently pay more.
Several top employers reached maximum salary estimates above $300K in the dataset.






