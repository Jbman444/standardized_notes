# Learn PostgreSQL

[Youtube Video](https://youtu.be/qw--VYLpxG4)


## What is a database
### data can be
    ⁃    Store
    ⁃    Manipulate
    ⁃    retrieve

Structured Query Language

### example
### first specify column name followed by the table Name
```postgresQL
SELECT first_name FROM person
```
data is stored in tables that consist of columns and rows

### relational database
    ⁃    tables can references each other
    ⁃    overall this is useful because we can split and organize data into separate tables so all data is accounted without overwhelming a single table.
### benefits of using PostgreSQL
    ⁃    open source
    ⁃    reliable
    ⁃    popular

### ?????

DB server - computer server
Client - What you use to connect to the database

### create a database

the standard is to use capitals to represent sql commands
```postgresql
CREATE DATABASE test;
```
    ⁃    name of the database created is test
psql
# terminal command used to start communication with server

### commands start with a backslash
\help
info on SQL commands1
\q
quit
\?
get more help related to psql commands
\l
list all available databases

## start

### this is a dash dash to help show all the options
psql —help

connection
-h database host or socket directory
-U database username
-p data server port

```postgresql
psql -h localhost -p 5432 -U amigoscode test
```
### host name followed by
    ⁃    default port
    ⁃    default username
    ⁃    name of database

### if you are trying to connect to a database that doesn’t exist you’ll get an error

psql
\l
shows you all available databases
\c test
connect to database
### this is how you switch between bases

### To delete a database

``` postgresql
DROP DATABASE test;
```
### however this is a very dangerous command
### therefore it is important to have a backup of your database
semi colon is what tells the terminal to execute a command

## How to create a table
### command
CREATE TABLE table_name (
    Column name + data type + constraints if any
)

### example
``` postgresql
CREATE TABLE person (
    id int,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    gender VARCHAR(6)
    data_of_birth     TIMESTAMP,
)
```
### What does this example do
creates a table named person
with a column of integers followed by
    ⁃    first_name column of characters limited to 50
    ⁃    last_name column of characters limited to 50
    ⁃    gender column of characters limited to 6
    ⁃    date_of_birth where the data type is time stamp ( includes hour and minute)

list of data types available
[link](https://www.postgresql.org/docs/current/datatype.html)

PAUSE ON VIDEO 44 MINUTES

```postgresql

\c test
CREATE TABLE person (
id INT,
first_name VARCHAR(50),
last_name VARCHAR(50),
gender VARCHAR(7),
date_of_birth DATE );
```
### Table is now made

\d
    ⁃    see all the available tables in my database
\d person
    ⁃    info related to a specific tabel (in this case person)

## Creating tables with constraints

### To delete a table
DROP TABLE person;

### table with constraints
``` postgresql
CREATE TABLE person(
id BIGSERIAL NOT NULL PRIMARY KEY,
first_name VARCHAR(50) NOT NULL,
last_name VARCHAR(50) NOT NULL,
gender VARCHAR(7) NOT NULL,
date_of_birth DATE NOT NULL,
email VARCHAR(150) );
```

creates tables and sequence
- BIGSERIAL is a data type that automatically generates a unique integer
    ⁃    NOT NULL means you must always have a value
    ⁃    PRIMARY KEY = UNIQUE + NOT NULL
    ⁃    UNIQUE duplicates of values can exist
    ⁃    email is option due to the lack of NOT NULL

## HOW to insert records into tables

``` postgresql

INSERT INTO person (
first_name,
last_name,
gender,
date_of_birth)
VALUES (‘Anne’, ‘Smith’, ‘FEMALE’, DATE ‘1988-01-09’);

```
\d
to see everything available
\dt
to see just the tables

### Making mock files
mockaroo
view .sql file using vscode

\?
see available options
\i filepath/person.sql

SELECT * FROM person
view all available data from person