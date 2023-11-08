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
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);

```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/05ffd82d-1cbe-4b06-95db-875359dcd19c)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![Screenshot 2023-10-18 173110](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/c69050ce-eb3b-438a-8e2b-4a7bfc7fdf1b)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![Q3](https://github.com/abinayasangeetha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393675/5e34fa0e-672f-4860-ab8d-d6430226f451)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```

### OUTPUT:

![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/22a26a2f-293a-45a3-8f04-2261774f4a2c)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/9bb4ee71-a4fd-43e9-b0c6-fbffd71e9e37)



### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/fe970747-6122-440d-a876-70fb0fbd9506)



### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/99a4cf01-63de-40c4-b4fc-bd6f372a57ba)



### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/a8577692-48a8-4055-a52d-3086cdffc049)



### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![ep 2,9](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/61003160-09e2-43df-b038-ecfa34759b1b)



### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/738a43ae-2dd7-45fb-8590-c7fe01d3de80)



### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/76ab0b21-72c4-4bb2-b408-dcc9268e77a9)


### Q12) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/950074c7-3de5-4bee-b52f-37b74ec248a5)



### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:

### MAXIMUM:
```
select max(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/38c9860d-e20b-4376-a18a-85b89df53449)


### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/621720b9-d2e7-433c-a21a-290fdec58ceb)


### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/7d8b3058-82fa-444d-9aa6-288927ea5ce2)
95f73030c)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/35815ab4-a2a2-44e2-8c60-615e41215701)


## Result:
 To create a manager database and execute DML queries using SQL is executed successfully.
