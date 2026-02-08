```sql
CREATE DATABASE iilm;

USE iilm;

CREATE TABLE Student(
-> student_id INT PRIMARY KEY,
-> first_name VARCHAR(50) NOT NULL,
-> last_name VARCHAR(50) NOT NULL,
-> email VARCHAR(100) NOT NULL UNIQUE,
-> dob DATE NOT NULL,
-> course VARCHAR(50) NOT NULL,
-> fees DECIMAL(8,2) CHECK(fees > 0 ));

INSERT INTO Student VALUES
-> (1,'Bhavya','Kamra','bhavya@gmail.com','2006-02-24','btech',90000),
-> (2,'Kaushal','Kishor','kaushal@gmail.com','2006-02-10','btech',90000),
-> (3,'Riya','Verma','riya@gmail.com','2006-09-24','btech',90000);

ALTER TABLE Student
-> ADD COLUMN City VARCHAR(20) DEFAULT 'DELHI';

INSERT INTO Student
-> (student_id, first_name, last_name, email, dob, course, fees)
-> VALUES
-> (4,'Neha','Singh','nehagmail.com','2006-02-21','BTECH',92000);

SELECT * FROM Student;

DESCRIBE Student;
```
