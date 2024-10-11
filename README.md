# MySQL---Creating-and-Joining-Tables

DAY 16 and DAY 17: Challenge 17 and 20

Created by: NABIL SHAJAHAN

As part of a 75-day data analysis challenge, this work on MySQL covers creating new tables, as well as joining these tables to retrieve required data. This work also covers altering tables such as adding column, dropping column, truncating table, and dropping table.


CREATE DATABASE Challenge;

USE Challenge;

CREATE TABLE Country (
Country_ID INT PRIMARY KEY NOT NULL,
Country_Name VARCHAR(50),
Population INT );

ALTER TABLE Country ADD COLUMN Area INT;

DESC Country;

INSERT INTO Country (Country_ID,Country_Name,Population,Area) VALUES
(101, 'India', 1435579517, 3000000),
(102, 'China', 1425475799, 9400000),
(103, 'USA', 340962176, 9100000),
(104, 'Canada', 38138369, 9900000),
(105, 'UK', 67081601, 243600),
(106, 'Indonesia', 278742819, 1900000),
(107, 'Brazil', 217074617, 8400000),
(108, 'Russia', 144182453, 16400000),
(109, 'Nigeria', 226601456, 910800),
(110, 'Ethiopia', 128203292, 1100000);

SELECT * FROM Country;

CREATE TABLE Persons (
ID INT PRIMARY KEY NOT NULL,
Fname VARCHAR(50),
Lname VARCHAR (50),
Population INT,
Rating DECIMAL(5,2),
CountryID INT, 
Country_Name VARCHAR(50),
FOREIGN KEY (CountryID) REFERENCES Country(Country_ID)
);

INSERT INTO Persons (ID,Fname,Lname,Population,Rating,CountryID,Country_Name) VALUES
(451, 'Abhi', 'Sinha', 1435579517, 3.4, 101, 'India'),
(452, 'Michael', 'Clayton', 340962176, 4.2, 103, 'USA'),
(453, 'Johnny', 'English', 67081601, 4.0, 105, 'UK'),
(454, 'Hal', 'Jordan', 38138369, 3.9, 104, 'Canada'),
(455, 'John', 'Grisham', 340962176, 4.4, 103, 'USA'),
(456, 'Sidhu', 'Anand', 1435579517, 4.6, 101, NULL),
(457, 'Mike', 'Myers', 38138369, 3.0, 104, 'Canada'),
(458, 'Thomas', 'Anderson', 340962176, 2.6, 101, NULL),
(459, 'Thomas', 'Shelby', 67081601, 3.3, 105, 'UK'),
(460, 'Raylan', 'Givens', 217074607, 3.8, 107, NULL);


DESC Persons;

SELECT * FROM Persons;

SELECT Persons.CountryID, Persons.Fname,
Persons.Country_Name, Country.Population
FROM Persons INNER JOIN Country
ON Persons.CountryID = Country.Country_ID;

SELECT DISTINCT Country_Name,
Country_ID FROM Country
UNION
SELECT DISTINCT Country_Name,
CountryID FROM Persons;


ALTER TABLE Country DROP COLUMN Population;

TRUNCATE TABLE Country;

DROP TABLE Country;


![Day 16](https://github.com/user-attachments/assets/27e2ee16-4772-482a-9b77-9c1329abe103)



![DAY 16 II](https://github.com/user-attachments/assets/f80b643d-2bad-4cba-9da4-ebce897c568e)



![Day 16 III](https://github.com/user-attachments/assets/33b0e1a5-d65a-4c81-bb0e-98c8b2d9e69b)




![Day 16 IV](https://github.com/user-attachments/assets/8aee4286-e9b2-4711-9e20-7985341e665b)
