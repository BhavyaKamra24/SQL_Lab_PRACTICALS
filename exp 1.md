# practical question-1 :-
## create database.
```sql
CREATE DATABASE bhavya_kamra;

USE bhavya_kamra;
```
## create department table.
```sql
CREATE TABLE Department (
-> DepNo INT PRIMARY KEY,
-> DName VARCHAR(15) NOT NULL) ENGINE=InnoDB;
```
## create employee table.
```sql
CREATE TABLE Employee (
-> EmpNo INT PRIMARY KEY,
-> EName VARCHAR(20) NOT NULL,
-> Job VARCHAR(20),
-> Mgr INT,
-> HireDate DATE,
-> Sal INT(10),
-> Comm INT,
-> DepNo INT,
-> FOREIGN KEY (DepNo) REFERENCES Department(DepNo)) ENGINE=InnoDB;
```
## inserting values in department table.
```sql
INSERT INTO Department VALUES
-> (10, 'RESEARCH'),
-> (20, 'ACCOUNTING'),
-> (30, 'SALES'),
-> (40, 'OPERATIONS');
```
## inserting values in employee table.
```sql
INSERT INTO Employee VALUES
-> (7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20),
-> (7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30),
-> (7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 500, 30),
-> (7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20),
-> (7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30),
-> (7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30),
-> (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 10),
-> (7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000, NULL, 40),
-> (7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 10),
-> (7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30),
-> (7876, 'ADAMS', 'CLERK', 7788, '1981-12-13', 1100, NULL, 20),
-> (7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30),
-> (7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);
```

# QUERIES:

## PRACTICAL QUESTION 1:

### Create Employee_master Table
```sql
CREATE TABLE Employee_master AS 
SELECT * FROM Employee;
```
### Delete Employee_master Table
```sql
DELETE FROM Employee_master
WHERE DepNo = 10;
```
### Update Employee_master Table
```sql
UPDATE Employee_master
SET Sal = Sal + (Sal * 0.10)
WHERE DepNo = 20;
```
### Alter Employee_master Table
```sql
ALTER TABLE Employee_master
-> MODIFY Sal DECIMAL(10,2);
```
### Drop Employee_master Table
```sql
DROP TABLE Employee_master;
```
----




