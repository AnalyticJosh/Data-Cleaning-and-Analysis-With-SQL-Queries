# Data Cleaning and Analysis With SQL Queries

**Overview**

This project demonstrates the use of SQL for cleaning and analyzing datasets. It showcases various techniques to handle common data issues, including duplicates, missing values, and inconsistent formats, while ensuring data integrity. The ultimate goal is to prepare raw data for analysis and generate actionable insights.

### Objectives

- Perform data cleaning tasks to standardize and validate datasets.
- Utilize SQL queries to handle missing data, transform columns, and remove inconsistencies.
- Explore and analyze cleaned data to uncover patterns and insights.

### Key Features

- Handling Duplicates: Removal of duplicate rows using window functions and subqueries.
- Data Transformation: Conversion of columns into appropriate data types and normalization.
- Dealing with Missing Values: Identification and treatment of null or incomplete records.
- Data Validation: Ensuring consistency and integrity post-cleaning.
- Exploratory Data Analysis (EDA): Generating descriptive statistics and uncovering trends.

### Technologies Used
- SQL: Primary language for data manipulation and analysis.
- Database Systems: Works with SQL-based platforms like MySQL, PostgreSQL, or SQL Server.
- Visualization (Optional): Power BI or Tableau for showcasing insights from cleaned data.
Dataset Information

Steps to Reproduce

Clone the Repository:

git clone https://github.com/AnalyticJosh/Data-Cleaning-and-Analysis-With-SQL-Queries.git
cd Data-Cleaning-and-Analysis-With-SQL-Queries

Set Up the Environment:

Install and configure a SQL database (e.g., MySQL, PostgreSQL).

Import the dataset into the database using SQL commands or tools like Data Import Wizard.

Run SQL Scripts:

Execute the provided scripts in the following order:

data_cleaning.sql: Performs initial cleaning tasks like removing duplicates and fixing formats.

eda.sql: Generates descriptive statistics and insights from the cleaned data.

Optional Visualizations:

Use tools like Tableau or Power BI to create dashboards based on the cleaned data.

Sample Queries

Removing Duplicates

WITH RowNumCTE AS (
    SELECT *, ROW_NUMBER() OVER (PARTITION BY unique_key ORDER BY created_at DESC) AS RowNum
    FROM dataset_table
)
DELETE FROM dataset_table
WHERE RowNum > 1;

Handling Missing Values

UPDATE dataset_table
SET column_name = 'Default Value'
WHERE column_name IS NULL;

Transforming Data Types

ALTER TABLE dataset_table
MODIFY column_name DATETIME;

## Results and Insights

- Removed over 15% of duplicate records, ensuring data accuracy.
- Standardized date formats, enhancing usability for analysis.
- Addressed missing values in key metrics, improving dataset completeness.

### Contributions

Contributions are welcome! If you have suggestions or improvements, please create a pull request.

### License

This project is licensed under the MIT License.

For further inquiries or feedback, please contact Joshua Amusan.
