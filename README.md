# Crowdfunding-ETL

## Overview of Project
A client requested analysis of their crowdfunding data. These data were firstly analyzed and data cleaning was performed. Finally, it was uploaded to the SQL database and tables were created.

### Resources

### Datasets:
- crowdfunding.xlsx
- backer_info.csv

### Software: 
- Python 3. 9. 12
- Jupyter Notebook 6. 4. 8
- Pandas 1. 4. 2
- Numpy 1. 21. 5

### Other Sources: 
- pgAdmin 4
- PostgreSQL 15.0
- QuickDBD

## Overview of the Analysis (ETL Process)
The data in the customer-provided "crowdfunding.xlsx" dataset is first transferred to the Python DataFrame. These data were separated into categories and subcategories, and a DataFrame was created and then transferred to the computer as a csv file. Classification of these data makes analysis easy. In the DataFrame contact information, keys and values are determined between the lines by list comprehension.

Previously created DataFrames for category and subcategories are merged and some unnecessary columns are dropped. One of them is the contact_id column. It is first extracted from the contact information and added to the DataFrame required for crowdfunding analysis. Being an integer is an important rule.

After the exported csv files are ready, ERD, in other words Entity Relationship Diagram, is drawn in order to explain the relationship between the columns in the table. Help is taken from QuickDBD for drawing this diagram. When the columns belonging to our data sets are used together with the data types and if we know our data set well, if the Primary Key and Foreign Keys are determined, it is possible to reveal the diagram easily. This diagram will show us the relationship between the data. When the schema SQL file obtained from the ERD diagram is run for the creation of the tables, validation is done.

## Results 

First of all, it should be explained that in the ETL process, the data must first go through the extraction and transformation phase. This stage contains the data "categories.csv" and "subcategories.csv".

In the Transformation section, the data cleaning process takes place in order to make better analyzes. In order to be able to analyze in Jupyter Notebook, after creating the DataFrame from the two-page .xlsx file given to us by the customer, extraction and transformation processes must be performed. After cleaning the data given by the customer, "campaign.csv", "contacts.csv" data were created in the transformation phase. In order to complete this part of the ETL phase, the "backers.csv" file is exported as a result of transferring the "backers_info.csv" data set given to us to the DataFrame in Jupyter Notebook.

Finally, at the Loading stage, which was requested from us for the study, after the tables were transferred to the SQL database, the SQL analysis requested from us was made and the relationship table was revealed with the Entity Relationship Diagram (ERD). The SQL file of the ERD scheme is exported.

Tables of these data will be added below to be explained.

#### Table 1. Category
<img width="361" alt="category" src="https://user-images.githubusercontent.com/26927158/199852166-f0919f79-efe3-4e59-ac5b-62bced901373.png">
The process of separating the category & subcategory column in the “crowdfunding.xlsx” file has been done. It is obvious that each row has a category and subcategory. For this reason, this distinction is necessary for a more explanatory analysis. It can be said that there are 9 categories in total.
The category_id and category_name columns show the designated category number for each category. The table for this data is in the "category.csv" file.



