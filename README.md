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

#### Table 2. Subcategory
![subcategory](https://user-images.githubusercontent.com/26927158/199852971-6eb8d4c9-788c-4ad6-9aa8-aba61fa05468.png)

Table 2 is formed as a result of assigning the id numbers of each subcategory. Each subcategory in this table is associated with the category table. However, for a broader view of the data, it must be separated into category and subcategory. In the above table, there are 24 subcategorys in total.
The data of this table is in the "subcategory.csv" file.

#### Table 3. Contacts
<img width="593" alt="contacts" src="https://user-images.githubusercontent.com/26927158/199852913-f9657290-11c9-4950-a549-62cd3cdee04d.png">
The table above, taken from the "Contacts.csv" file, shows the first 10 rows of the dataset. Data columns; It is present as contact_id, first_name, last_name and email. The table includes the column names as well as the data types.

#### Table 4. Campaign
![campaign](https://user-images.githubusercontent.com/26927158/199853166-f258a11a-929a-4e2c-ae4d-d63846a3a8f5.png)
Looking at the above dataset, the columns can be seen. In addition to the data in our "crowdfunding.xlsx" dataset, category_id and subcategory_id columns have been added.

#### Table 5. Backers Data
<img width="536" alt="backers_data" src="https://user-images.githubusercontent.com/26927158/199853293-b498da55-89a2-4bd7-a86d-1742eb02681b.png">
In the above table, the columns are separated by transferring the data from the "backers_info" table to the DataFrame. And the first 10 columns are seen as above. In the table content; There is information about the backer_id, cf_id, name and email columns.
Table 5 belongs to the "backers data.csv" file, and no cleaning process or lost data analysis has been done in the file.

#### Table 6. Backers
<img width="650" alt="backers" src="https://user-images.githubusercontent.com/26927158/199853526-c4c73560-fc06-4e6e-9cb8-bda68a2fdcb6.png">
Table 6 shows that, unlike Table 1, the name column is separated into first name and last name. Also, table 2 belongs to the file "backers.csv", which is the dataset of the cleaned data.

#### Table 7. Email Contacts Remaining Goal Amount
<img width="674" alt="email_contacts_remaining_goal_amount" src="https://user-images.githubusercontent.com/26927158/199853747-0f583a32-b3f1-49da-894c-810b7783c10e.png">
In this data set, the remaining goal amount values of the people belonging to each row are included. The table consists of 14 rows and the target values are listed from largest to smallest. The e-mails and surnames of the persons are also included in the table.

#### Table 8. Email Backers Remaining Goal Amount
<img width="975" alt="email_backers_remaining_goal_amount" src="https://user-images.githubusercontent.com/26927158/199853964-9cbcea4c-0d61-447d-ac0e-d3a521e4bb84.png">
Table 8 shows the remaining goals of the supporters. In this table, there are columns such as email, first_name, last_name, cf_id, company_name, description, end_date, left of gal. The remaining_goal_amount column shows the values we have. First name column is ordered from Z. The surname also has an alphabetical order effect. There is a correct display from the very end of the list to the beginning.

#### Table 9. Crowdfunding DB Relationships Data
<img width="401" alt="Screen Shot 2022-11-03 at 4 27 21 PM" src="https://user-images.githubusercontent.com/26927158/199854142-c8db72b6-d800-4730-a4b7-2878cecffba3.png">
#####backers
<img width="390" alt="Screen Shot 2022-11-03 at 4 27 46 PM" src="https://user-images.githubusercontent.com/26927158/199854145-af735ec2-0d4d-4364-b947-8df4d686b250.png">
Above is a table extracted from the QuickDBD website. The names and data types of the columns belonging to the campaign, category, sabcategory, contacts and backers datasets in this table are included. Using this table, the relationship between the data is determined.

#### Diagram 1. Crowdfunding DB Relationships
![crowdfunding_db_relationships](https://user-images.githubusercontent.com/26927158/199854388-917007c7-3619-4518-9aa5-1990d46b56b0.png)

In the diagram above, there are primary key and foreign keys for each data set. In the table containing the columns of the Campaign dataset, cf_id is the primary key, while contact_id, category_id and subcategory_id are foreign keys.
Looking at the column names of the contacts table, contact_id is the primary key.
While category_id is the primary key in category dataset, subcategory_id is primary key in sucategory dataset.
In the backers data set, backer_id is the primary key and cf_id is the foreign key. The column in a dataset that relates to other tables is called a foreign key.
This diagram allows us to accurately explain the relationship between data and datasets.




















