#SQL Queries

## Using SQL as a Tester
- Getting data for testing
- Saving data
- Data verification in databases (Find data, ensure integrity, manipulate test data)
- Testing

## Using SQL as a PMO/BA
- Systems teams use databases in development
- To analyse data you must retrieve it
- Can allow you to help in test phase
- Helps youunderstand data flow

## SQL Syntax
SELECT -> DISTINCT -> FROM -> WHERE -> GROUP BY -> HAVING -> ORDER BY

Example
```
SELECT ContactName AS 'Name', Phone AS 'Phone Number', CONCAT(City, ', ', Country, ', ', PostalCode) AS 'Full Address' FROM Customers
WHERE Country = 'France' AND City = 'Paris'
ORDER BY PostalCode ASC
```

## Wildcards
- % (Represents zero or more characters) Ex. bl% finds bl, black, blue and blob
- _ (Represents a single character) Ex. h_t finds hot, hat and hit
- [ ] (Represents any single character within the brackets) Ex. h[oa]t finnds hot and hat, but not hit
- ^ (Represents any character not in the brackets) Ex. h[^oa]t finds hit, but not hot and hat
- - (Represents aa range of characters) Ex. c[a-b]t finds cat and cbt

## Arithmetic Operators
- + Add (can be used on DATETIME columns)
- - Subtract (can be used on DATETIME columns)
- * Multiply 
- / Divide
- % Percentage (Ex 12%5 = 2 because the remainder of 12/5 is 2)

## Order By
Used to order queries based upon a criterea in ASC (ascending) or DESC (descending)
```
ORDER BY <column_name> DESC or ASC
```
## AS
This is used to rename a column title in the query but does not affect the database.
```
SELECT <column_name> AS 'chosen_name'
```
