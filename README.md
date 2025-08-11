# SQL-TASK-5
create database ORDER_LIST;
USE ORDER_LIST;

-- Customers table
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100),
    City VARCHAR(100)
);


-- Insert Customers
INSERT INTO Customers (CustomerID, Name, City) VALUES
(1, 'Alice', 'New York'),
(2, 'Bob', 'Los Angeles'),
(3, 'Charlie', 'Chicago'),
(4, 'Diana', 'Miami');

-- Orders table
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE,
    CustomerID INT,
    Amount DECIMAL(10, 2)
);

-- Insert Orders
INSERT INTO Orders (OrderID, OrderDate, CustomerID, Amount) VALUES
(101, '2025-08-01', 1, 250.00),
(102, '2025-08-03', 1, 300.00),
(103, '2025-08-04', 2, 150.00),
(104, '2025-08-05', 5, 400.00); 

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;



-- two ways for FULL JOIN
SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID

UNION

SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Orders
LEFT JOIN Customers ON Customers.CustomerID = Orders.CustomerID;




-- FULL JOIN SECOND WAY
SELECT Customers.Name, Orders.OrderID, Orders.Amount
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;


