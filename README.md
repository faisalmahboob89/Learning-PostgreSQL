# Learning-PostgreSQL

* [Introduction to PostgreSQL](#introduction-to-postgresql)
* [Windows Installation](#windows-installation)

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
