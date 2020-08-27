# Learning-PostgreSQL

* [Introduction to PostgreSQL](#introduction-to-postgresql)
* [Windows Installation](#windows-installation)
* [Create Database](#create-database)
* [Connect to Database](#connect-to-database)
* [Drop Database](#drop-database)
* [Creating Table](#creating-table)
* [Dropping Table](#dropping-table)
* [SELECT FROM](#select-from)
* [ORDER BY](#order-by)

# Introduction to PostgreSQL:
PostgreSQL is an open source relational database management system (DBMS) developed by a worldwide team of volunteers. PostgreSQL is not controlled by any corporation or other private entity and the source code is available free of charge.
## Notes:
- PostgreSQL is the most advanced Open Source Relational Database Management System and we can run multiple version together
- What shall database do?
  - It will store, manipulate and retrieve data in DB.
- Database resides in a server.
- Postgres is a DB engine.
- We will use **psql** shell.

# Windows Installation:
Download the PostgreSQL from https://www.postgresql.org/. Please, follow the below steps:

- Go to www.postgresql.org
- Click on Download
- Click on Windows
- Click on Download the Installer
- Download the desired version as per your System Type(64 bit or 32 bit)
Now, complete the setup of the downloaded .exe file just like any other programs. Provide a password for **Superuser** while doing the setup and remember this password must. Finish the setup. A SQL Shell(psql) and a graphical user interface pgAdmin4 will be installed for operating the database. In this demonstartion, using of SQL Shell(psql) will be in focus. Click the psql application to launch it. The psql command-line program will display. Enter all the necessary information such as the server, database, port, username, and password. To accept the default, press Enter. Provide the password that you entered during installing the PostgreSQL.

```
Server [localhost]:
Database [postgres]:
Port [5432]:
Username [postgres]:
Password for user postgres:
psql (11.8)
WARNING: Console code page (437) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.

```

## Notes:
- PostgreSQL server is a DB server
- pgAdmin is a GUI Client
- Stack Builder is some additional drivers
- Command line tools- CLI client, SQL Shell(psql)
- We can connect to DB server in three ways- CMD/CLI, GUI Client, Application
- Some GUI Clients are- Datagrip, Postico, pgAdmin
- psql shell is seperately provided in Windows. But we can also use the command psql in windows cmd by declaring environment variable. We can directly access psql through cmd in Linux because of Linux installation procedure being different than Windows. PostgreSQL installation in linux will be added later. 

- For accessing the database through GUI from browser, click on **pgAdmin**.

![gui](https://github.com/faisalmahboob89/Learning-PostgreSQL/blob/master/GUI.PNG)

- We can use postgresql through cmd in mac also. The default shell in mac is **zsh**. We will need to set the environment variable for running psql from anywhere.
- We need to use backslash(\) before every adminitrative command.
For help:
```
\?
```
For listing all DB's:
```
\l
```

- We can run psql through default cmd shell. But we need to do it by setting the environment variable and making the psql command global. But using the psql shell is better than this.
- If we don't select any DB, we will directly enter into the default DB.

## Create Database:
For creating database, put commands or run query like below:
```
CREATE DATABASE test;
```
## Connect to Database:
For connecting to any database, put the commands like below:
```
\c test
```
## Drop Database:
For dropping a database, use DROP command. But be aware before using the DROP command.
```
DROP DATABASE test;
```
## Creating Table:
Execute commands like below for creating table in any database. Connect to the database at first and then create table.

CREATE TABLE table_name(
column_name + data_type() + constraints if any
);
```
CREATE TABLE person (
id BIGSERIAL NOT NULL PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
gender VARCHAR(7) NOT NULL,
date_of_birth DATE NOT NULL,
email VARCHAR(150) );
```
#### Notes:
- Use **\d** for listing all tables in DB with sequence
- Use **\d table_name** for seeing table descriptions
- Use **\dt** for only listing the tables without sequence
- **not null** represents that the value can not be blank and the value must be provided. If we don't provide any value, it will automatically take it as null.
- **BIGSERIAL** variable can increment on its own. If we use this variable, a sequence "table_id_seq" is created which can be seen by **\d** command. It cannot be dropped because there is a dependency with the main table (DB.table.id).

## Dropping Table:
```
DROP TABLE person;
```
This command will fully delete the table. We can check it by \d command.

##Insert into Database:
For inserting data into a table, execute command like this- 
INSERT INTO person (col_name1, col_name2....) VALUES ('value1', 'value2');

```
INSERT INTO person (first_name, last_name, gender, date_of_birth)
VALUES ('Anne', 'Smith', 'FEMALE', date '1988-01-09');
```
We did not mention any **id**. But it will auto increment because of the BIGSERIAL variable.
If we don't provide any email address, it will be accepted because the email variable is not declared as "not null".

#### Notes:
- The date variable must be in yy-mm-dd format.
#### Mockaroo:
- We can generate data by using **mockaroo** data generator for performing and checking the database queries. We need a large number of data for performing the database quieries and it is a lengthy process to insert data one by one and then test those with quiery. Go to [mockaroo](https://www.mockaroo.com/) for generating your data and the download the .sql file. Open the file using any code editor like Atom, Sublime, VSCODE etc. We will generate 1000 rows of data in a table.
- mockaroo will automatically run DB query and generate 1000 values. Then we can download it in a .sql file.
- Using the VSCode IDE is the best for working with SQL related queries.
- Insert the file's data to the table by executing commands like this:
```
\i /Users/HP/person.sql
```

## SELECT FROM:
This query mainly performs read operation. We can view data from the table.
```
SELECT * FROM person;
SELECT FROM person; (it will show no data)
SELECT first_name FROM person;
SELECT first_name, second_name FROM person;
SELECT email FROM person;
```

## ORDER BY:
This query mainly performs sorting. We can view data in ascending order or in descending order. When we click a specific column and the data is shown in ascending or descending order, that column is the **order by** column.
The default order is **asc**. For showing data in descending order, we have to type **desc**.
```
SELECT * FROM person ORDER BY id ASC;
SELECT * FROM person ORDER BY country_of_birth DESC;
SELECT * FROM person ORDER BY first_name;
```

