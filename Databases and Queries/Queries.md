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

## String Functions
- SUBSTRING used to 
```
SUBSTRING (expression, start, length)
```

- CHARINDEX - finds the index value of the search term
```
CHARINDEX('<search_term>', '<column_name>')
```

- LEFT or RIGHT - finds first or last characters
```
LEFT(<column_name>, <value>) 
RIGHT(<column_name>, <value>)
```

- LTRIM or RTRIM - Removes spaces at beginning or end of a string

- LEN - finds the length of the search term
```
LEN(<column_name>)
```

- REPLACE - replaces chosen term with a chosen value
```
REPLACE(<column_name>, '<target_value' , '<replacing_value')
```

- UPPER or LOWER - converts to upper or lower case
```
UPPER(<column_name>)
LOWER(<column_name>)
```

## Date Functions
- GETDATE - returns current date and time
```
GETDATE()
```

- SYSDATETIME - returns date and time of the computer being used
```
SYSDATETIME()
```

- DATEADD - adds to a date
```
DATEADD(<day,month or year>, <value_added>, <date1>)
```

- DATEDIFF - finds the difference in date
```
DATEADD(<day,month or year>, <date1>, <date2>)
```

- YEAR - extracts year from a date
```
YEAR(<date>)
```

- MONTH - extracts month from a date
```
MONTH(<date>)
```

- DAY - extracts day from a date
```
DAY(<day>)
```

## Aggregate Functions
- SUM - finds the total of a column for all rows selected
```
SUM(<column_name>)
```

- AVG - finds the average of a column for all rows selectd
```
AVG(<column_name>)
```

- MIN - finds the minimum value of a column for all rows selected
```
MIN(<column_name>)
```

- MAX - finds the maximum value of a column for all rows selected
```
MAX(<column_name>)
```

- COUNT - counts number of NOT NULL rows selected
```
COUNT(<column_name>)
or
COUNT(*)
```

## Cases
```
SELECT CASE
WHEN <argument> THEN '<display_1>'
ELSE '<display_2>'
END AS "<column_name>"
FROM 
```

## GROUP BY
- Used to provide sub totals
```
GROUP BY <column_names>
```
 
## HAVING
- Used insted of where when filtering on subtotals / grouped data
- Cannot use aliases 

```
HAVING <subtotal>
HAVING <grouped_data>
```
