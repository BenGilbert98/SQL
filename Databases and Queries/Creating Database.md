# Databases and Queries

## Data Types
- VARCHAR - Adaptable to different lengths of characters. Records MAX size
- CHARACTER or CHAR - Data must be at a fixed length. Fixed amount of space used.
- INT - Holds a whole number / integer value, positive or negative
- DATE or TIME or DATETIME - Stores Date, Time or both date and time
- DECIMAL or NUMERIC - Fixed Precision and scale (digits to right of decimal point) numbers.
- BINARY - Use to store binary data such as an image or file
- FLOAT - Scientific use (very large numbers)
- BIT - Equvalent to binary (0, 1 or NULL)

### Examples
(image)

## Creating Databases and Tables
```
CREATE DATABASE <database_name>;

CREATE TABLE <table_name>(
    <column_1> <datatype>
    <column_2> <datatype>
    etc...
);
```

## Commands
This section will show commands to create and modify tables.
### Alter
Can be used to RENAME, MODIFY, ADD or DROP columns or change to NOT NULL 
Examples below:
``` 
ALTER TABLE <table_name>
ADD release_date DATETIME;

ALTER TABLE <table_name>
ALTER COLUMN <column_name> <datatype>
```

### Insert
Inserts columns into your tables with specified values
Example below:
```
INSERT INTO <table_name> (
    <first_column>, <second_column> ... 
)
VALUES (
    <value_1>, <value_2>
);
- VARCHAR, CHAR and DATE all use quotes for their VALUES
- An INSERT statement including DECIMAL and INT does not use and quotes

### Create Table
Creates a table inside a database
Example below:
```
CREATE TABLE <table_name>(
<column_1> <datatype>,
<column_2> <datatype>,
...
);
```

### Update 
Updates values inside of a table
Example below:
```
UPDATE <table_name>
    SET <column_name> = <value>
    WHERE <column_name> = <value>
```
