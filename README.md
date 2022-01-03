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
