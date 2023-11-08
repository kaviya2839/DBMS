# EX 3 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```python
sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```

## insert the following values into the table
```python
sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```python
update manager set salary=salary+(salary*0.10);
```

### OUTPUT:
![1](https://github.com/Leann4468/DBMS/assets/121165979/981b813f-7e6a-4983-a9e6-71e5b36c4659)


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```python
delete from manager where salary<2750;
```

### OUTPUT:
![2](https://github.com/Leann4468/DBMS/assets/121165979/b7d5be38-dcea-4d0b-9321-63c5ef745471)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```python
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![3](https://github.com/Leann4468/DBMS/assets/121165979/85d54b25-c890-47b5-894d-f2f48baf94f8)


### Q4)	List the names of Clerks from emp table.


### QUERY:
```python
select ename from manager where designation='clerk';
```

### OUTPUT:
![4](https://github.com/Leann4468/DBMS/assets/121165979/6ec71fdf-9635-46a6-8140-d5574991f811)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```python
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![5](https://github.com/Leann4468/DBMS/assets/121165979/b680be1c-701d-4461-ae2c-00cf9aa82277)


### Q6)	List the names of employees not eligible for commission.

### QUERY:
```python
select ename from manager where commission=0;
```

### OUTPUT:
![6](https://github.com/Leann4468/DBMS/assets/121165979/92b81a0e-baa0-4046-a727-4cc8417ca281)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```python
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![7](https://github.com/Leann4468/DBMS/assets/121165979/7d48cbb5-719f-4e8f-8ef2-dce76dff05e5)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```python
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/a8577692-48a8-4055-a52d-3086cdffc049)



### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```python
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');

```
### OUTPUT:
![ep 2,9](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/61003160-09e2-43df-b038-ecfa34759b1b)



### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```python
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/738a43ae-2dd7-45fb-8590-c7fe01d3de80)



### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```python
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/76ab0b21-72c4-4bb2-b408-dcc9268e77a9)


### Q12) Find number of rows in the table EMP

### QUERY:
```python
 select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/950074c7-3de5-4bee-b52f-37b74ec248a5)



### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```python
select max(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/38c9860d-e20b-4376-a18a-85b89df53449)


### MINIMUM:
```python
select min(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/621720b9-d2e7-433c-a21a-290fdec58ceb)


### AVERAGE:
```python
select avg(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/7d8b3058-82fa-444d-9aa6-288927ea5ce2)
95f73030c)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```python
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/35815ab4-a2a2-44e2-8c60-615e41215701)


## Result:
 To create a manager database and execute DML queries using SQL is executed successfully.
