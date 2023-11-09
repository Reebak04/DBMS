# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL

## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```python
sql
create table employee(
emp_id numeric,
emp_name varchar(10),
addr varchar(40)
);
```


### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/56bbda44-a582-42e3-9738-5b1d035dd675)



### Q2) Insert three rows into emploee table 



### QUERY:
```python
sql
insert into employee values(1,'Luffy','EastBlue');
insert into employee values(2,'Shanks','GodValley');
insert into employee values(3,'Grap','MarinFord');
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/db081e71-759d-44df-b847-75294a2e2a34)


### Q3) Start the transaction and create a save point A.

### QUERY:
```python
sql
savepoint A;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/d491985f-d652-4510-baba-69bda39920c4)


### Q4) Perform insertion into employee table.

### QUERY:
```python
sql
insert into employee(4,'Robin','EniesLobby');
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/b9d81949-f840-4fb4-8427-6c5efb79da74)



### Q6)	Display the employee table and create a save point s2 .


### QUERY:
```python
sql
select * from employee;
savepoint s2;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/bc86bb69-d7ad-4193-aeda-050214882984)



### Q7)	Perform updation on any one of the row.


### QUERY:
```python
sql
update employee set emp_name='Nico Robin' where emp_id=4;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/2e9e6855-56ea-40f4-ba36-56f8eafd68ee)



### Q8) Display the employee table and rollback to  save point s2 


### QUERY:
```python
sql
select * from employee;
rollback to s2;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/b66b2852-7cbc-49e6-a059-579485f3ff49)


### Q9) Display the employee table and commit the changes; 


### QUERY:
```python
sql
select * from employee;
commit;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/7dd55645-f515-4c5b-9174-1b3a9bc24e30)


### Q10) Rollback to save point s1;

### QUERY:
```python
sql
rollback to A;
```

### OUTPUT:
![image](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/441afff5-9f95-418b-ad8b-c2b5cfbf810d)



## RESULT :
Thus the basic TCL and DCL commands are executed.
