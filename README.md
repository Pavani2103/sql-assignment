
-- 1.Desgin the above database with following table by applying Primary key and Foreign key

-- OrderItem Table
create table OrderItem(id int PRIMARY KEY, OrderId int, ProductId int, UnitPrice decimal(12,2), Quantity int);

-- Product Table
create table Product(id int PRIMARY KEY, ProductName nvarchar(50), UnitPrice decimal(12,2), Package nvarchar(30), isDiscontinued bit);

-- Orders Table
CREATE TABLE Orders (id int PRIMARY KEY, OrderDate DATETIME, OrderNumber nvarchar(10), CustomerId int, TotalAmount decimal(12,2))

-- Customer Table
CREATE TABLE Customer (id int PRIMARY KEY, FirstName nvarchar(40),LastName nvarchar(40),City nvarchar(40), Country nvarchar(40),Phone nvarchar(20));

----------------------------------------------

--Adding Primary & Foreign Key
ALTER TABLE Orderitem
ADD FOREIGN KEY(ProductId) REFERENCES Product(id);

ALTER TABLE Orderitem
ADD FOREIGN KEY(ProductId) REFERENCES Product(id);

ALTER TABLE Orders
ADD FOREIGN KEY(CustomerId) REFERENCES Customer(id);

------------------------------------------------

-- 2.Insert Records in all tables 
INSERT INTO PRODUCT(id, ProductName, UnitPrice, Package, isDiscontinued) VALUES(51, 'Bottle', 3400.00, 'yes', 0);
INSERT INTO PRODUCT(id, ProductName, UnitPrice, Package, isDiscontinued) VALUES(52, 'Jug', 2500.00, 'no', 1);
INSERT INTO PRODUCT(id, ProductName, UnitPrice, Package, isDiscontinued) VALUES(53, 'Table', 5000.00, 'no', 0);
INSERT INTO PRODUCT(id, ProductName, UnitPrice, Package, isDiscontinued) VALUES(54, 'Chair', 4500.00, 'yes', 1);
INSERT INTO PRODUCT(id, ProductName, UnitPrice, Package, isDiscontinued) VALUES(55, 'Mixer', 3400.00, 'yes', 0);

------------------------------------------
INSERT into Orders(id, OrderDate, OrderNumber, CustomerId, TotalAmount) VALUES(101, 12-03-2022, 'OD771', 1, 2200.00);

INSERT into Orders(id, OrderDate, OrderNumber, CustomerId, TotalAmount) VALUES(102, 12-03-2022, 'OD772', 2, 3500.00);
INSERT into Orders(id, OrderDate, OrderNumber, CustomerId, TotalAmount) VALUES(103, 12-03-2022, 'OD773', 3, 4785.00);
INSERT into Orders(id, OrderDate, OrderNumber, CustomerId, TotalAmount) VALUES(104, 12-03-2022, 'OD774', 4, 1452.00);
INSERT into Orders(id, OrderDate, OrderNumber, CustomerId, TotalAmount) VALUES(105, 12-03-2022, 'OD775', , 7458.00);

----------------------------------------------------

Insert into OrderItem(id, OrderId, ProductId, UnitPrice, Quantity) VALUES (401, 101, 51, 
2200.00, 2);
Insert into OrderItem(id, OrderId, ProductId, UnitPrice, Quantity) VALUES (402, 102, 52, 
2800.00, 4);
Insert into OrderItem(id, OrderId, ProductId, UnitPrice, Quantity) VALUES (403, 103, 53, 
3200.00, 8);
Insert into OrderItem(id, OrderId, ProductId, UnitPrice, Quantity) VALUES (404, 104, 54, 
4522.00, 10);
Insert into OrderItem(id, OrderId, ProductId, UnitPrice, Quantity) VALUES (405, 105, 55, 
8956.00, 5);

-------------------------------------------------------------

INSERT INTO Customer (id, FirstName, LastName, City, Country, Phone) VALUES (1,'Ram', 'Verma', 'Mumbai', 'India', '941257438')
INSERT INTO Customer (id, FirstName, LastName, City, Country, Phone) VALUES (2, 'Ram', 'Verma', 'Mumbai', 'India', '891255638')
INSERT INTO Customer (id, FirstName, LastName, City, Country, Phone) VALUES (3,'John', 'Hoden', 'America', 'USA', '125478932')
INSERT INTO Customer (id, FirstName, LastName, City, Country, Phone) VALUES (4,'Rashmi', 'Dixit', 'Bangalore', 'India', '741258930')
INSERT INTO Customer (id, FirstName, LastName, City, Country, Phone) VALUES (5,'Sunny', 'Peterson', 'Kanpur', 'India', '012547896')

-------------------------------------------

-- 4.In Order table OrderDate should not accept null value
ALTER TABLE Customer 
ALTER Column FirstName nvarchar(40) NOT NULL;

--------------------------------------------

-- 5.Display all customer details
ALTER TABLE Orders
ALTER COLUMN OrderDate datetime NOT NULL;

---------------------------------------------

-- 6.write a query to display Country whose name starts with A or I

Select * from Customer WHERE Country LIKE 'i%' or Country LIKE 'a%'

----------------------------------------------
-- 7 .write a query to display whose name of customer whose third character is i

Select * from Customer WHERE FirstName LIKE '__i%'
