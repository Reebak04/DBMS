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
UPDATE manager SET salary = salary + (salary *10/100);
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/d5d26bf7-0ef5-46b6-84c2-c62968b9d3c8)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary < 2750;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/b2218bd4-ca4f-4e09-988e-aa68fb90b190)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annualsalary" from manager;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/baca0db8-92b3-4879-b578-fd355783f598)

### Q4)	List the names of Clerks from emp table.
### QUERY:
```
select * from manager
where designation = 'clerk';
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/2ea314f8-7533-47ee-ae2a-848637409483)

### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select * from manager
where designation != 'manager';
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/2739414c-a082-47b5-9104-6644e76be91b)


### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select * from manager
where commission=0;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/c4b5eeec-55d9-4ac4-8538-642417eb2045)


### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager
where ename like('s%') or ename like('%s');
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/f041ba0e-8756-485d-9bec-406efd4765fa)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/d23befc2-933c-4895-81a2-73d8fc676e5f)

### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/0c5b4d20-39fb-4dbb-a1eb-9c2c3a2ebeb8)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/0d27410d-a290-497a-a2b4-5c37a9a3e657)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager
where deptno != 30 and deptno != 40 and deptno != 10;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/cbc33c9d-6e38-4f46-97d2-43cfb3ac2669)

### Q12) Find number of rows in the table EMP
### QUERY:
```
select count(enum) from manager;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/66114e71-612c-42af-b5fa-b4486dbeea74)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/3649365b-3cd8-4231-aa88-fae24a72d243)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/Reebak04/DBMS/assets/118364993/a8be794a-7c97-4d77-b613-65f6c66fd465)

## RESULT :
Thus the basic DML commands are executed.
