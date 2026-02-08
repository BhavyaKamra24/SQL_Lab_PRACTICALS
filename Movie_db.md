``` sql

CREATE DATABASE movie_db;

USE movie_db;

CREATE TABLE Movie(
-> MovieID INT PRIMARY KEY,
-> MovieName VARCHAR(50) NOT NULL,
-> Category VARCHAR(30) NOT NULL,
-> ReleaseDate DATE,
-> ProductionCost DECIMAL(10,2) CHECK(ProductionCost > 0),
-> BuinessCost DECIMAL(10,2) DEFAULT 0);

INSERT INTO Movie VALUES
-> (1,'Hindi_Movie','Musical','2018-04-23',124500,130000),
-> (2,'Tamil_Movie','Action','2016-05-17',112000,118000),
-> (3,'English_Movie','Horror','2017-08-06',245000,360000),
-> (4,'Bengali_Movie','Adventure','2017-01-04',72000,100000),
-> (5,'Telugu_Movie','Action',NULL,10000,0),
-> (6,'Punjabi_Movie','Comedy',NULL,30500,0);

SELECT MovieID, MovieName, BuinessCost
-> FROM Movie;

SELECT DISTINCT Category
-> FROM Movie;

SELECT MovieID, MovieName,(BuinessCost - ProductionCost) AS NetProfit
-> FROM Movie;

SELECT MovieID, MovieName, ProductionCost
-> FROM Movie
-> WHERE ProductionCost > 80000 AND ProductionCost < 125000;

SELECT *
-> FROM Movie
-> WHERE Category IN ('Comedy','Action');

SELECT *
-> FROM Movie
-> WHERE ReleaseDate IS NULL;

DESCRIBE TABLES;

SELECT * FROM movie;
```