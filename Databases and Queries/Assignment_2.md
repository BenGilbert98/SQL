# SQL Querying Assignment 2

## How many orders in NWDB?
```
SELECT COUNT(OrderID) AS 'Number of Orders' FROM Orders
```
## How many orders have the ship city as Rio de Janerio?
```
SELECT COUNT(OrderID) AS 'Number of Orders From Rio de Janerio' FROM ORDERS
WHERE ShipCity = 'Rio de Janerio'
```
## Select all orders that have the ship city as Rio de Janerio or Reims
```
SELECT * FROM ORDERS
WHERE ShipCity IN ('Rio de Janerio', 'Reims')
```
## Select all of the entries where the company name has a z or a Z in the table of customers
```
SELECT CompanyName FROM Customers
WHERE CompanyName LIKE '%z%'
```
## Find the name of all companies that we do not have the FAX numbers, also find who to speak with, contact number and city
```
SELECT ContactName AS 'Who To Speak To', Phone, City FROM Customers
WHERE Fax IS NULL
```
## Re-target all of our customers in Paris get information on these clients
```
SELECT CompanyName AS 'Company', ContactName AS 'Contact Name', ContactTitle AS 'Title', Address, PostalCode, Phone AS 'Phone Number', Fax FROM Customers
WHERE City = 'Paris'
```
## Who orders the most out of these clients and who are the top 5 clients
```
SELECT Customers.CustomerID, Orders.OrderID,[Order Details].Quantity AS 'Quantity Ordered', [Order Details].UnitPrice AS 'Price Per Unit', [Order Details].Quantity * [Order Details].UnitPrice AS 'Total Price' FROM Customers 
INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
INNER JOIN [Order Details]
ON Orders.OrderID = [Order Details].OrderID
WHERE City = 'Paris'

SELECT SUM(Quantity) AS 'Total Quantity Orded By SPECD' FROM [Order Details]
WHERE OrderID IN (10738, 10907, 10964, 11043)

SELECT SUM(UnitPrice * Quantity) AS 'Total Value Of All Orders' FROM [Order Details]
WHERE OrderID IN (10738, 10907, 10964, 11043)
```
## Which deliveries took longer than 10 days? Display the Business name, contact name, and contact details as well as the number of deliveries that were overdue
```
SELECT Orders.OrderID, Orders.RequiredDate, Orders.ShippedDate, DATEDIFF(DAY, Orders.ShippedDate, Orders.RequiredDate) AS 'Days to Deliver', Customers.CompanyName AS 'Business Name', Customers.ContactName AS 'Contact Name', Customers.Phone AS 'Phone Number', Customers.Fax AS 'Fax'  FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID
WHERE ShipCity = 'Paris' AND 'Days to Deliver' > '10'
```
