#Task


## ERD
![](C:\Users\bengi\Sparta\SQL\Databases and Queries\Images\ERD.png)


## Azure Code
```
CREATE TABLE users(
    user_id INT NOT NULL IDENTITY (1,1) PRIMARY KEY,
    email VARCHAR (100) NOT NULL,
    phone_number VARCHAR (11) NOT NULL,
    full_name VARCHAR (100) NOT NULL 
);

CREATE TABLE ebooks(
    book_id INT NOT NULL IDENTITY (1,1) PRIMARY KEY,
    book_title VARCHAR (255) NOT NULL,
    book_location VARCHAR (255) NOT NULL,
    release_date DATE,
    author_id INT REFERENCES (user_id),
    genre VARCHAR (100) NOT NULL
);

CREATE TABLE booking(
    booking_id INT NOT NULL IDENTITY (1,1) PRIMARY KEY,
    buyer INT REFERENCES users(user_id),
    ebook_purchased INT REFERENCES ebooks(book_id),
    date_purchased DATE,
    price DECIMAL (4,2)
);
```
