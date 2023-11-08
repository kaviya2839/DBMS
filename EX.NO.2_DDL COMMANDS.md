# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb
### SQL QUERY:
```python
create database student_db;
```
### OUTPUT:
![1](https://github.com/Leann4468/DBMS/assets/121165979/48c4c935-32c1-4cae-b375-e68cba5d2d3c)


### 2) Create a table student with the following fieds RegisterNumber,Name,Age,Address,Phone number
### SQL QUERY: 
```python
create table student(Regno int,Name varchar(20),Age int,Address varchar(50),Phonenumber varchar(10));
```
### OUTPUT:
![2](https://github.com/Leann4468/DBMS/assets/121165979/5f248ecb-5f4c-4f71-9de8-50076e7f53b1)

### 3) Alter the above student table by adding another attribute department
### SQL QUERY: 
```python
alter table student
add dept varchar(20);
```
### OUTPUT:
![3](https://github.com/Leann4468/DBMS/assets/121165979/b669e9f2-1fc6-4e3f-9398-8dbe9d854f9e)


### 4) Drop the student table
### SQL QUERY: 
```python
drop table student;
```
### OUTPUT:
![4](https://github.com/Leann4468/DBMS/assets/121165979/7478394a-5dbe-44af-9869-9bcc014e9c35)


### 5) Delete the student table using truncate keyword
### SQL QUERY:
```python
truncate table student;
```
### OUTPUT:
![5](https://github.com/Leann4468/DBMS/assets/121165979/a16962e1-e389-4947-bb93-bd2b79e3e226)

### 6) Rename the student table to mystudent
### SQL QUERY: 
```python
alter table student
rename to mystudent;
```
### OUTPUT:
![6](https://github.com/Leann4468/DBMS/assets/121165979/47655109-2cd5-41f3-ba1c-2a704d546eea)

## Result:
  Thus the basic DDL commands in SQL are executed. 


