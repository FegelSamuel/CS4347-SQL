SQL is a high level Structured Query Language for databases. 

I would recommend [sqlbolt](sqlbolt.com) for learning SQL.

# Overview
Our description is based on SQL-92 or SQL2 and some extensions from SQL:1999 and SQL:2003. Not all examples here may work on your particular system, but maybe ChatGPT can help you translate to whatever you're using. 

<br>

SQL is a DDL (Data Definition Language).

## Domain Types
Domain types are also known as data types
### Basic Domain Types
* `char(n)`: a fixed length character **string**.
* `varchar(n)`: a variable length character **string**.
* `int/interger`: an integer.
* `smallint`: a small integer.
* `numeric(p,d)`: a fixed pointer number with user-specified precision. `p` being precision for total amount of digits (not including the `.`) and `d` being the precision beyond the decimal point.
  * An example is `numeric(5,2)` can give us the maximum value of: `999.99` and minimum value of `0.00`.
* `real`, `double precision`: floating point and double-precision floating point numbers.
* `float(n)`: a floating point number.
### Additional Domain Types (SQL2 ONLY, CHECK YOUR SYSTEM)
* `DATE`: Made up of `year-month-day` in the format `yyyy-mm-dd`
* `TIME`: made up of `hour:minute:second` in the format `hh:mm:ss`
* `TIME(i)`: Made up of `hour:minute:second` plus `i` additional digits
* TIMESTAMP: Has both `DATE` and `TIME` components ('2002-09-27 09:12:47')


## Schema Definition
### Create Table
```SQL
create table r
  (A_1D_1,
  A_2D_2,
  ...,
  A_nD_n,
  (integrity constraint_1),
  ...
  (integrity constraint_n))
```
`r` is the name of your relation.

Each `A_i` is an attribute name in the schema of relation `r`.

`D_i` is the data type of values int he domain of attribuet `A_i`

#### Example
```SQL
create table branch
  (branch_name    char(15),
  branch_city     char(30),
  assets          integer)
```

## Integrity Constraints
DO NOT DO THIS
```SQL
create table branch
  (branch_name    char(15)  PRIMARY KEY,
  branch_city     char(30)  PRIMARY KEY,
  assets          integer)
```
If you want branch name and city to be unique, what you can do is that you can make a tuple between name and city the primary key.
```SQL
primary key (A1, A3)
```
### PRIMARY KEY
The chosen minimal set that represents a given entity in your database uniquely.
### UNIQUE
Any minimal set that represents a given entity in your database uniquely (**Candidate Key**).
### NOT NULL
Retake Discrete Math (and maybe CS1) if you don't know this one
### FOREIGN KEY
Some UNIQUE or PRIMARY KEY of some other table. A table with a foreign key effectively has a reference to whatever table it has a relation to. 

# Retrieval Queries
## INSERT
```SQL
insert into branch
  values('Perryridge', 'Dallas', null)
```
Attribute list can be omitted if it is the same as in CREATE TABLE
NULL and DEFAULT values can be specified
## DELETE
Deleting all tuples from a relation
```SQL
delete from branch
```
Delete specific tuple
```SQL
delete from branch where 'Dallas'
```
## DROP TABLE
Delete the whole relation lol
```SQL
DROP TABLE DEPENDENT
```
## ALTER TABLE
* The alter table command is used to add or delete attributes to an existing relation:
```SQL
alter table branch add phone_number char(10)
alter table branch drop branch_city
```

# As of writing this on March 26th, the lecture ends about here. Will make more when the lecture gets to more. 

# Specifying Updates

# Relational Views
