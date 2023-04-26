# Crowdfunding_ETL

## Introduction

ETL (Extract, Transform & Load) is a foundational skill. In the real world, data is everywhere and often scattered across multiple sources, and it can be messy. Understanding how to extract, load, and transform data is a critical concept as it enables you to have clean, up-to-date, and accurate data. It empowers you to become an expert in your data by allowing you to manipulate data types, fix formatting issues, and create additional columns to enrich and gain meaningful insights from your data. In this project, I will be using the data below to perform extraction, transformation, and loading of the data.

## Sources of data

Within Resources Folder:
*  contacts.xlsx
*  crowdfunding.xlsx

## Database Type for Final Production Environment

Description: The proposal includes specifying the type of database that will be used for the final production environment to store and manage the data.

* Database Type: Relational (SQL)
* Data Cleaning and Processing: Jupyter Notebook
* Packages Used: pandas, numpy, datetime
* Data Loading: pgAdmin

The proposal includes specifying the type of database that will be used for the final production environment to store and manage the data, as well as the tools and packages used for data cleaning and processing. A relational (SQL) database will be used for the final production environment. Data cleaning and processing will be performed using Jupyter Notebook with the following packages: pandas, numpy, and datetime. The cleaned data will be loaded into the relational database using pgAdmin for storage and management. Additionally, an Entity Relationship Diagram (ERD) of the tables will be created using a tool like https://www.quickdatabasediagrams.com/ to provide a visual representation of the database structure.

<strong>ERD</strong><br>
![ERD](https://raw.githubusercontent.com/Hamim-Hussain/Crowdfunding_ETL/main/ERD.PNG)


## Findings

1. The "theater" category had the highest success rate, "Journalism" and "games" categories had relatively low success rates.
2. The "plays" subcategory had the highest number of successful projects, with 187 out of 319 projects being successful, indicating a relatively high success rate.
3. "Theater" category had the highest sum of pledged amounts, with a total of $15,763,227, followed by "film & video", "music", "publishing", and "technology" categories, indicating higher crowdfunding support in these categories compared to others such as "journalism" and "games".
4. The United States (US) had the highest sum of pledged amounts, with a total of $31,409,336, followed by Canada (CA) with $2,812,788, and the United Kingdom (GB) with $2,192,705, indicating significant crowdfunding activity in these countries.

## Conclusion

Overall, the data suggests that "theater", "film & video", and "music" are the most successful categories in terms of crowdfunding projects, while "journalism" and "games" have relatively low success rates. Similarly, "plays", "photography books", "web", "food trucks", and "wearables" subcategories have relatively high success rates, while "audio", "science fiction", and "world music" have lower success rates. The United States, Canada, and the United Kingdom have the highest total sum of pledged amounts, indicating higher crowdfunding support in these countries compared to others.

# Project Outline

## Instructions
The instructions for this mini project are divided into the following subsections:

* Create the Category and Subcategory DataFrames
* Create the Campaign DataFrame
* Create the Contacts DataFrame
* Create the Crowdfunding Database

## Create the Category and Subcategory DataFrames
1. Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:
* A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories
* A "category" column that contains only the category titles
2. Export the category DataFrame as category.csv and save it to your GitHub repository.
3. Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:
* A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories
* A "subcategory" column that contains only the subcategory titles
4. Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository.

## Create the Campaign DataFrame
1. Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns:
* The "cf_id" column
* The "contact_id" column
* The "company_name" column
* The "blurb" column, renamed to "description"
* The "goal" column, converted to the float data type
* The "pledged" column, converted to the float data type
* The "outcome" column
* The "backers_count" column
* The "country" column
* The "currency" column
* The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format
* The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
* The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
* The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame
2. Export the campaign DataFrame as campaign.csv and save it to your GitHub repository.

## Create the Contacts DataFrame
1. Choose one of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:
* Option 1: Use Python dictionary methods.
* Option 2: Use regular expressions.
2. If you chose Option 1, complete the following steps:
* Import the contacts.xlsx file into a DataFrame.
* Iterate through the DataFrame, converting each row to a dictionary.
* Iterate through each dictionary, doing the following:
- Extract the dictionary values from the keys by using a Python list comprehension.
- Add the values for each row to a new list.
* Create a new DataFrame that contains the extracted data.
* Split each "name" column value into a first and last name, and place each in a new column.
* Clean and export the DataFrame as contacts.csv and save it to your GitHub repository.
3. If you chose Option 2, complete the following steps:
* Import the contacts.xlsx file into a DataFrame.
* Extract the "contact_id", "name", and "email" columns by using regular expressions.
* Create a new DataFrame with the extracted data.
* Convert the "contact_id" column to the integer type.
* Split each "name" column value into a first and a last name, and place each in a new column.
* Clean and then export the DataFrame as contacts.csv and save it to your GitHub repository.

## Create the Crowdfunding Database
1. Inspect the four CSV files, and then sketch an ERD of the tables by using QuickDBDLinks to an external site..
2. Use the information from the ERD to create a table schema for each CSV file.
3. Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository.
4. Create a new Postgres database, named crowdfunding_db.
5. Using the database schema, create the tables in the correct order to handle the foreign keys.
6. Verify the table creation by running a SELECT statement for each table.
7. Import each CSV file into its corresponding SQL table.
8. Verify that each table has the correct data by running a SELECT statement for each.
