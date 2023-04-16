# PostgreSQL
Consist of various tutorials and scripts for learning PostgreSQL. These scripts serve as a valuable resource for learning and implementing new skills, techniques, or workflows, making it an invaluable asset for those seeking to expand their knowledge and proficiency in a particular domain.

## Table of Contents
1. What is a Database?
2. SQL and Relational Databases
3. Installation
4. Creating a Database


### What is a Database?
A database serves as a location where data can be stored, managed, and retrieved. Typically, this data is stored in a computer's server. Essentially, you input data into the database, and then you have the ability to view, manipulate, delete, and update the data using various operations provided by the database. 

### SQL and Relational Databases
Postgre is a popular database engine. The language used to interact with the database is SQL, which stands for Structured Query Language. SQL allows us to perform operations on the database, such as selecting specific columns from a table using commands like "SELECT", specifying columns and tables with reserved keywords like "FROM", and managing data in a relational database.

In a relational database, data is stored in tables which are formed by columns and rows. For example, a "person" table might have columns like ID, first name, last name, gender, and age, and rows containing actual data. SQL allows us to manage data in a relational database, where tables can have relationships with each other. For instance, a "person" table might have a relationship with a "car" table, where a person can have a corresponding car with a car ID. This structure helps to organize and manage data efficiently.

Relational databases are widely used on the internet and are essential for anyone learning programming. They provide a structured way to store and manage large amounts of information. Unstructured tables can make it difficult to query and perform operations on data. Therefore, relational databases with well-defined relationships between tables are preferred for effective data management. Postgres and SQL are powerful tools for working with relational databases, and learning SQL is essential for anyone interested in programming and working with data.
### Installation
PostgreSQL is available for Windows, Mac, and Linux. The installation process is straightforward and can be completed in a few minutes.
Head over to https://www.postgresql.org/download/ and download the installer for your operating system. Follow the instructions to complete the installation process.
Next open up the SQL shell downloaded with the PostgreSQL installation. You can do this by searching for "psql" in the start menu. This will open up the SQL shell, which is where we will be writing our SQL commands. 
pgAdmin is a graphical user interface for PostgreSQL. It is a powerful tool for managing databases and performing operations on them. It is not necessary to use pgAdmin, but it is a useful tool for those who are new to SQL. You can download pgAdmin from https://www.pgadmin.org/download/. Follow the instructions to complete the installation process. or get it it downloaded from the start installation procedure.

##Commands
To list all the databases -> \l

### Creating a Database
To create a database, we use the "CREATE DATABASE" command. For example, to create a database called "test", we would write the following command:
```sql      
CREATE DATABASE test;
```