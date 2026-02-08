```sql
CREATE DATABASE bhavya_kamra;

USE bhavya_kamra;

CREATE TABLE Department (
-> DepNo INT PRIMARY KEY,
-> DName VARCHAR(15) NOT NULL) ENGINE=InnoDB;

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

INSERT INTO Department VALUES
-> (10, 'RESEARCH'),
-> (20, 'ACCOUNTING'),
-> (30, 'SALES'),
-> (40, 'OPERATIONS');

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

SHOW TABLES;

DESC Employee;

DESC Department;

## QUERIES:
# PRACTICAL QUESTION 1:

## Create Employee_master Table
CREATE TABLE Employee_master AS 
SELECT * FROM Employee;

## Delete Employee_master Table
DELETE FROM Employee_master
WHERE DepNo = 10;

## Update Employee_master Table
UPDATE Employee_master
SET Sal = Sal + (Sal * 0.10)
WHERE DepNo = 20;

## Alter Employee_master Table
ALTER TABLE Employee_master
-> MODIFY Sal DECIMAL(10,2);

## Drop Employee_master Table
DROP TABLE Employee_master;

# PRACTICAL QUESTION 2:

##  List all distinct job in Employee.
SELECT DISTINCT Job 
FROM Employee;

## List all info about employees in DepNo 30
SELECT * 
FROM Employee 
WHERE DepNo = 30;

## Find DepNo > 20
SELECT DepNo 
FROM Employee 
WHERE DepNo > 20;

## Managers and Clerks in DepNo 30
SELECT *
FROM Employee
WHERE DepNo = 30
AND Job IN ('MANAGER','CLERK');

## EName, EmpNo, DepNo of all Clerks
SELECT EName, EmpNo, DepNo
FROM Employee
WHERE Job = 'CLERK';

## Managers not in DepNo 30
SELECT *
FROM Employee
WHERE Job = 'MANAGER' AND DepNo <> 30;

## Employees in department 10 who are not Managers and Clerks
SELECT *
FROM Employee
WHERE DepNo = 10
AND Job NOT IN ('MANAGER','CLERK');

## Employees earning between 1200 and 1400
SELECT EName, Job
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;

## EName, DepNo of Clerk,Analyst,Salesman
SELECT EName, DepNo
FROM Employee
WHERE Job IN ('CLERK','ANALYST','SALESMAN');

## Employee whose name starts with M
SELECT EName, DepNo
FROM Employee
WHERE EName LIKE 'M%';

# PRACTICAL QUESTION 3:

## Employees & Jobs - DepNo 30 Desc Salary
SELECT EName, Job, Sal
FROM Employee
WHERE DepNo = 30
ORDER BY Sal DESC;

## 5 Letter Names Start A End N
SELECT EName, DepNo
FROM Employee
WHERE EName LIKE 'A___N';

## Names Starting with S
SELECT EName
FROM Employee
WHERE EName LIKE 'S%';

## Names Ending with S
SELECT EName
FROM Employee
WHERE EName LIKE '%S';

## DepNo 10,20,30 OR Job Clerk,Salesman,Analyst
SELECT EName
FROM Employee
WHERE DepNo IN (10,20,40) OR Job IN ('CLERK','SALESMAN', 'ANALYST');

## Employees with Comm
SELECT EName, EmpNo
FROM Employee
WHERE Comm IS NOT NULL;

## Employee Total Salary
SELECT EmpNo, (Sal + IFNULL(Comm,0)) AS Total_Salary
FROM Employee;

## Employee Annual Salary
SELECT EmpNo, (Sal + IFNULL(Comm,0)) * 12 AS Annual_Salary
FROM Employee;

## Clerk Salary > 3000
SELECT EName
FROM Employee
WHERE Job = 'CLERK' AND Sal > 3000;

## Clerk,Salesman,Analyst Salary > 3000
SELECT EName
FROM Employee
WHERE Job IN ('CLERK', 'SALESMAN' 'ANALYST') AND Sal > 3000;
```





