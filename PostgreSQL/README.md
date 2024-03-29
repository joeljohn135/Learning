# PostgreSQL
Consist of various tutorials and scripts for learning PostgreSQL. These scripts serve as a valuable resource for learning and implementing new skills, techniques, or workflows, making it an invaluable asset for those seeking to expand their knowledge and proficiency in a particular domain.

## Table of Contents
1. [What is a Database?](#what-is-a-database)
2. [SQL and Relational Databases](#sql-and-relational-databases)
3. [Installation](#installation)
4. [Commands](#commands)
5. [Creating, acessing,deleting a Database](#creatingaccessingdeleting-a-database)
6. [Create and delete table](#create-table)
7. [Important Data Types](#important-data-types)
8. [Inserting, updating, deleting, and selecting data](#inserting-updating-deleting-and-selecting-data)
9. [Operations](#operations)
<br/>
😵‍💫Troubleshooting

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

## Commands
To list all the databases -> \l
To connect to a database -> \c database_name
To list the relations(table) -> \d
To list the columns of a table -> \d table_name
### Creating,Accessing,Deleting a Database
To create a database, we use the "CREATE DATABASE" command. For example, to create a database called "test", we would write the following command:
```sql      
CREATE DATABASE test;
```
Opening a database 
```sql
psql -h localhost -p 5432 -U postgres test
```
OR
```sql
\c test
```
Deleting a database
```sql
DROP DATABASE test;
```
### Create table
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
    ....
);
```
Example without Constraints:
```sql
CREATE TABLE person (
    id INT,
    first_name VARCHAR(255),
    last_name VARCHAR(255),
    age INT
);
```
Example with Constraints:
```sql  
CREATE TABLE person (
    id INT PRIMARY KEY,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    age INT NOT NULL
);
```
What is a Primary Key?
A primary key is a unique identifier for a row in a table. It is used to uniquely identify each row in a table. For example, a person table might have a primary key of "id", where each person has a unique ID. This is useful for identifying a specific person in the table. A primary key must be unique for each row in a table, and it cannot be NULL. A primary key can be a single column or a combination of multiple columns.
Another point to note is someting called BIGSERIAL. It is a special data type that automatically generates unique sequential integers. This is useful for creating a primary key column that increments by 1 for each new row. For example, we can create a "person" table with a primary key column "id" of type BIGSERIAL:
```sql
CREATE TABLE person (
    id BIGSERIAL PRIMARY KEY,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    age INT NOT NULL
);
```
Drop table
```sql
DROP TABLE table_name;
```

### Important Data Types:
* INT - integer
* VARCHAR - variable character length
* TEXT - long character length
* DATE - date
* BOOLEAN - true or false

Rest can be found in the link ->
https://www.postgresql.org/docs/current/datatype.html

### Inserting, updating, deleting, and selecting data
Inserting data
```sql  
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```
Example:
```sql
INSERT INTO person (first_name, last_name, age) 
VALUES ('John', 'Smith', 25);
```
### Operations
#### Selecting data
```sql
SELECT column1, column2, column3, ...
FROM table_name;
```
Example:
```sql
SELECT * FROM person;
```
#### Selecting specific columns
```sql
SELECT column1, column2, column3, ...
FROM table_name;
```
Example:
```sql
SELECT first_name, last_name FROM person;
```
#### Selecting specific rows
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE condition;
```
Example:
```sql
SELECT * FROM person
WHERE age > 30;
```
#### Selecting specific rows with AND
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```
Example:
```sql
SELECT * FROM person
WHERE age > 30 AND age < 40;
```
#### Selecting specific rows with OR
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```
Example:
```sql
SELECT * FROM person
WHERE age < 18 OR age > 60;
```
#### Selecting specific rows with IN
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name IN (value1, value2, value3, ...);
```
Example:
```sql
SELECT * FROM person
WHERE age IN (18, 25, 30);
```
#### Selecting specific rows with NOT
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE NOT condition;
```
Example:
```sql
SELECT * FROM person
WHERE NOT age = 30;
```
#### Selecting specific rows with BETWEEN
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```
Example:
```sql
SELECT * FROM person
WHERE age BETWEEN 18 AND 30;
```
#### Selecting specific rows with LIKE
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name LIKE pattern;
```
Example:
```sql
SELECT * FROM person
WHERE first_name LIKE 'J%';
```
#### Selecting specific rows with NULL
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name IS NULL;
```
Example:
```sql
SELECT * FROM person
WHERE first_name IS NULL;
```
#### Selecting specific rows with NOT NULL
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name IS NOT NULL;
```
Example:
```sql
SELECT * FROM person
WHERE first_name IS NOT NULL;
```
#### Selecting specific rows with DISTINCT
```sql
SELECT DISTINCT column1, column2, column3, ...
FROM table_name;
```
Example:
```sql
SELECT DISTINCT first_name FROM person;
```
#### Selecting specific rows with ORDER BY
```sql
SELECT column1, column2, column3, ...
FROM table_name
ORDER BY column1, column2, column3, ... ASC|DESC;
```
Example:
```sql
SELECT * FROM person
ORDER BY age DESC;
```
#### Selecting specific rows with LIMIT
```sql
SELECT column1, column2, column3, ...
FROM table_name
LIMIT number;
```
Example:
```sql
SELECT * FROM person
LIMIT 5;
```
#### Distinct
```sql
SELECT DISTINCT column1, column2, column3, ...
FROM table_name;
```
Example:
```sql
SELECT DISTINCT first_name FROM person;
```
#### offset
```sql
SELECT column1, column2, column3, ...
FROM table_name
OFFSET number;
```
Example:
```sql
SELECT * FROM person
OFFSET 5;
```
```sql
#### Arthmetic operations
```

```sql 
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name operator value;
```
Example:
```sql
SELECT * FROM person
WHERE age + 5 > 30;
```
Using both Limit and offset
```sql
SELECT column1, column2, column3, ...
FROM table_name
LIMIT number
OFFSET number;
```
Example:
```sql
SELECT * FROM person
LIMIT 5
OFFSET 5;
```
'OR' using Fetch 
```sql
SELECT column1, column2, column3, ...
FROM table_name
OFFSET number
fetch first number rows only;
```
#### Using IN 
```sql
SELECT column1, column2, column3, ...
FROM table_name
WHERE column_name IN (value1, value2, value3, ...);
```
Example:
```sql
SELECT * FROM person
WHERE age IN (18, 25, 30);
```
#### Using group by
```sql
SELECT column1, column2, column3, ...
FROM table_name
GROUP BY column1, column2, column3, ...;
```
Example:
```sql
SELECT first_name, COUNT(*) FROM person
GROUP BY first_name;
```
#### Using Order and group by and having
```sql 
SELECT column1, column2, column3, ...
FROM table_name
GROUP BY column1, column2, column3, ...
HAVING condition;
```
Example:
```sql
SELECT first_name, COUNT(*) FROM person
GROUP BY first_name
HAVING COUNT(*) > 1;
```
#### Using Sum,avg,min,max
```sql
SELECT SUM(column_name)
FROM table_name;
```
Example:
```sql
SELECT SUM(age) FROM person;
```
Example:
```sql
SELECT AVG(age) FROM person;
```
Example:
```sql
SELECT MIN(age) FROM person;
```
Example:
```sql
SELECT MAX(age) FROM person;
```
#### Using Round
```sql
SELECT ROUND(column_name, number)
FROM table_name;
```
Example:
```sql
SELECT ROUND(AVG(age), 2) FROM person;
```
#### Using Alias
```sql
SELECT column_name AS alias_name
FROM table_name;
```
Example:
```sql
SELECT first_name AS name FROM person;
```
#### Using Coleasce
```sql
SELECT COALESCE(column_name, 'value')
FROM table_name;
```

### Troubleshooting
Few problems i have faced were:
1. Not able to connect to psql bascically the terminal did not recognize "psql": solution is to add the path of the bin and lib folder of postgresql to the environment variables. The path will be found in the installation folder of postgresql.

2. Not able to connect to the database like they ask for your user password: solution is by writing the right command to access the database 
```sql
psql -h localhost -p 5432 -U postgres test
```