# PostgreSQL

> Installation

[Link to Install PostgreSQL](https://www.postgresql.org/download/)

## Working with the SQL Shell.

Server [localhost]: *(Press ENTER)* <br/>
Database [postgres]: *(Press ENTER or choose Database)* <br/>
Port [8000]: *(Press ENTER or enter Port)* <br/>
Username [postgres]: *(Press ENTER or enter Username)* <br/>
Password for user postgres: *(You must enter a Password)*

> Create and delete databases

Default database name: ***postgres***

With the help of this command you can see all commands in SQL Shell
``` bash
\?
```
With the help of this command you can see all databases
``` bash
\l
```
**CREATE DATABASE *database.name;*** — command to create a database <br/>
👇 command to switch to other databases 
``` bash
\c database.name
```
**DROP DATABASE *database.name;*** — command to delete a database <br/>
> Create tables

👇 command to create tables <br/>
**CREATE TABLE *table_name(<br/>
column_name + data_type + constraints (if any) <br/>
)***

With the help of this command you can see all tables
``` bash
\d
```
With the help of this command you can see anyone table
``` bash
\d table.name
```
**NOT NULL** — The user must enter it.
For example:
``` bash
email VARCHAR(150) NOT NULL
```
** PRIMARY KEY ** — Using primary keys we can create unique columns (it is impossible to repeat the same thing);
For example: 
``` bash
id BIGSERIAL NOT NULL PRIMARY KEY
```
👆 If you used ID number 1 you can't use it again.
**DROP TABLE table.name** — command to delete any tables.

👇 command to clear the SQL shell
``` bash
\! cls
```

**INSERT INTO table.name (column_name) VALUES (values for columns)** — command to add users(or something) to the table. <br/>
For example:
```bash
INSERT INTO employee (first_name, last_name, gender, email, date_of_birth) VALUES ('John', 'Doe', 'Male', 'Jd@mail.com', '2000-01-01');
```
👇 command to see number of users(or something) in the table.

``` bash
\dt employee
```
With [this site](https://mockaroo.com/) you can create a .sql file (for a table) for testing.

👇 command to import downloaded .sql file.
``` bash
\i path(for exampleC:/users/downloads/sqlname.sql)
```

> Queries for fetching data

**SELECT * FROM *table.name;*** — command to get all users(or something) in the table. <br/>
**SELECT FROM *table.name;*** — command to get number of users(or something) in the table. <br/>
**SELECT *column_name* FROM *table.name;*** - command to get just one column_name rows. <br/>
For example: 
```bash
SELECT first_name FROM employee;
```
Also you can get two or more column_name rows with the help of this command 👇
**SELECT *first_column_name*, *second_column_name* FROM *table.name;*** - command to get just one column_name rows. <br/>
For example: 
```bash
SELECT first_name, last_name FROM employee;
```
