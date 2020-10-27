# Task

We have been tasked with drawing out the DB to our amazing online book store startup called booksareus.io (this is an example)

The ideas is a Users can come in a rent out Ebooks to read! Amazing! Also User can choose to write a Ebook! Even more Amazing!


## Specifications

At the core of most product you have people or users. Let’s draw this out first.
We should have User

A user must have:

- email,
- phone number
- name.

Each Ebook has:

- title
- location
- release date
- User who create it!

Each booking has:

- what ebook
- who rented the book
- date
- price

Todo:

- Draw out the above tables
- Each field
- Add the foreign keys

Questions

- What is the relationship between the tables?
- Who belongs to whom?
- Can user rent out books?
- how many 1:N relationships are there?
- Do we have or do we need a N:N relationship?


## ERD
![](Images\ERD.png)


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
