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
```
Create a database studentdb;
```

### OUTPUT:
![Screenshot 2023-10-18 132226](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/5a11a8aa-8b92-4438-83c9-70c99fa2f6f1)


### 2) Create a table student with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```
 create table student(rollno int,name char(20),age int,address varchar(20),phoneno int);
```



### OUTPUT:
![Screenshot 2023-10-18 132258](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/b563cf0d-ff59-4fdf-b626-734eee9faf99)


### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
```
alter table student add department char(30);
```

### OUTPUT:
![Screenshot 2023-10-18 132314](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/934eecfe-19a6-472e-b1a3-cc6197b7e1be)



### 4) Drop the student table
 
### SQL QUERY: 
 ```
drop table student;
```


### OUTPUT:
![drop](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/85487739-adc7-4724-b193-a1c68232cf55)



### 5) Delete the student table using truncate keyword

### SQL QUERY: 
```
truncate table student;
```


### OUTPUT:
![truncate](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/32840a78-3656-4880-bd86-50dc5eefdb9a)




### 6) Rename the student table to mystudent

### SQL QUERY: 
```
alter table student rename to mystudent;
```




### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/484b8c3e-a0b0-49cd-974b-916e7e8aa739)



## Result:
         Thus the basic DDL commands in SQL are executed. 
