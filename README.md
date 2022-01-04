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
Also you can get two or more column_name rows with the help of this command 👇 <br/>
**SELECT *first_column_name*, *second_column_name* FROM *table.name;*** - command to get just one column_name rows. <br/>
For example: 
```bash
SELECT first_name, last_name FROM employee;
```
**
SELECT * FROM *table.name* ORDER BY *column_name* ASC(or DESC);** — command to sort alphabetically or vice versa.
If you are using ASC — alphabetically;
If you are using DESC — vice versa;

For example: 
``` bash
SELECT * FROM employee ORDER BY country_of_birth DESC;
```

**SELECT DISTINCT *column_name* FROM *table.name;*** — you can subtract exactly the same values once in a row; <br/>
For example:
``` bash
SELECT DISTINCT country_of_birth FROM employee ORDER BY country_of_birth DESC;
```
**SELECT * FROM *table.name* WHERE *column_name* = *'value';*** — you can find out which users exactly matches your request; <br/>
For example:
``` bash
SELECT * FROM employee WHERE gender = 'Female';
```
**SELECT * FROM *table.name* WHERE *first_column_name* = *'value';* AND *second_column_name* = *'value';*** — you can find out which users exactly matches your request; <br/>
For example:
``` bash
SELECT * FROM employee WHERE gender = 'Female' AND country_of_birth = 'Russia';
```
Also you can use this: 👇<br/>
For example: 
``` bash
SELECT * FROM employee WHERE gender = 'Female' AND (country_of_birth = 'Russia' OR country_of_birth = 'Ukraine');
```

**SELECT * FROM *table.name* LIMIT 20(or any number);** — you can get only 20 users(or something);<br/>
For example:
```bash
SELECT * FROM employee LIMIT 20;
```
Also you can use this: 👇<br/>
**SELECT * FROM *table.name* OFFSET 10 LIMIT 5;** — You can get 5 of the ID number users starting with the number 11. <br/>
Also you can use this: 👇<br/>
**SELECT * FROM *table.name* OFFSET 10 FETCH FIRST 5 ROW ONLY;** — You can get 5 of the ID number users starting with the number 11. <br/>

For example you used this: 👇<br/>
**SELECT * FROM employee WHERE country_of_birth = 'China' OR country_of_birth = 'Argentina' OR country_of_birth = 'Israel';** <br/>
But you can use the shorter version: 👇 <br/>
**SELECT * FROM employee WHERE country_of_birth IN('China', 'Argentina', 'Israel');** <br/>

**SELECT * FROM employee WHERE date_of_birth BETWEEN '2000-01-01' AND '2001-01-01';** — you can find users who was born between these times. <br/>
**SELECT * FROM employee WHERE email LIKE '%.com';** — you can find users whose email is created like this. <br/>
**SELECT country_of_birth, COUNT(*) FROM employee GROUP BY country_of_birth;** — you can get column country_of_birth rows in the table and count of countries. <br/>

**SELECT COALESCE(email, 'not applicable') FROM employee;** — you can change empty nullable rows to 'your text'.
> Aggregates and Basic Arithmetic
```bash
SELECT MAX(price) FROM holiday;
   max
---------
 9975.41


SELECT MIN(price) FROM holiday;
  min
--------
 100.65


SELECT AVG(price) FROM holiday;
          avg
-----------------------
 4919.1838716148445336
 
 SELECT ROUND(AVG(price)) FROM holiday;
 round
 -----
 4919
```

**SELECT SUM (price) FROM holiday;** — you can find a total price of something. <br/>
> Working with Date and Time

**SELECT NOW();** — you can know present full time. <br/>

Also you can use this: 👇 <br/>

**SELECT NOW()::DATE;**  — you can know present date. <br/>

**SELECT NOW()::TIME;** — you can know present time. <br/>

If it is 2022-01-01 and you are using this: 👇 <br/>

**SELECT NOW() - INTERVAL '10 YEAR';** <br/>

That will be the result: 2012-01-01 <br/>

Also you can use MONTH, WEEK or DAYS. <br/>

If it is 2022-01-01 and you are using this: 👇 <br/>

**SELECT NOW() + INTERVAL '10 YEAR';** <br/>

That will be the result: 2032-01-01 <br/>

Also you can use this: 👇 <br/>

**SELECT EXTRACT(YEAR FROM NOW())** <br/>

That will be the result: 2022 <br/>
And you can use MONTH, DAY, WEEK or DOW(day of the week) <br/>

> Primary Keys
