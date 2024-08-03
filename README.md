________________________________________
# 🚀 SQL Project: Library Management System 📚
I'm thrilled to share details about my recent SQL project: the development of an online Library Management System. This project is part of my ongoing learning in SQL and database management, and it has been an incredible opportunity to apply theoretical knowledge to a practical scenario.
# Project Overview
The Library Management System aims to enhance the efficiency of managing book issuances and returns in a college library. The system is designed to cater to both students and teachers, with distinct return periods for each group. Each book in the library has a unique identifier, even if there are multiple copies of the same book. The system records who issued the book, the duration of the issuance, and any fines that may be applicable.


# Key Tasks

# 1.	Database Creation with ER Diagram:

#	Identifying Entities and Attributes:
	Students: Includes attributes like StudentID, FirstName, LastName, Email, Phone, Department, and DateOfMembership.
	Teachers: Includes attributes like TeacherID, FirstName, LastName, Email, Phone, Department, and            DateOfMembership.
	Books: Includes attributes like BookID, Title, Author, ISBN, Publisher, YearPublished, and Category.
	IssuedBooks: Includes attributes like IssueID, BookID, IssuedToID, IssuedToType, IssueDate, ReturnDate, and FineAmount.
#	Designing the Database Schema: 
    Created a comprehensive ER diagram that maps out the relationships and attributes of each entity.
#	Establishing Relationships:
	One-to-Many relationship between Students and IssuedBooks (one student can issue multiple books).
	One-to-Many relationship between Teachers and IssuedBooks (one teacher can issue multiple books).
	One-to-Many relationship between Books and IssuedBooks (one book can be issued multiple times).

# ER Diagram Representation

Here's a simplified textual representation of the ER diagram:
[Students] <--(1:M)-- [IssuedBooks] --(M:1)--> [Books]
[Teachers] <--(1:M)—

# In this representation:
•	[Students] and [Teachers] each have a one-to-many relationship with [IssuedBooks].
•	[Books] has a one-to-many relationship with [IssuedBooks].

# Example SQL Scripts

# Here are some SQL scripts that I used to create the database tables and establish the relationships:
--Create Students Table
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    Phone VARCHAR(15),
    Department VARCHAR(50),
    DateOfMembership DATE
);
-- Create Teachers Table
CREATE TABLE Teachers (
    TeacherID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    Phone VARCHAR(15),
    Department VARCHAR(50),
    DateOfMembership DATE
);
-- Create Books Table
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    ISBN VARCHAR(20),
    Publisher VARCHAR(100),
    YearPublished YEAR,
    Category VARCHAR(50)
);
# Create IssuedBooks Table
CREATE TABLE IssuedBooks (
    IssueID INT PRIMARY KEY,
    BookID INT,
    IssuedToID INT,
    IssuedToType ENUM('Student', 'Teacher'),
    IssueDate DATE,
    ReturnDate DATE,
    FineAmount DECIMAL(10, 2),
    FOREIGN KEY (BookID) REFERENCES Books(BookID)
);

# Learning Outcomes

This project was a fantastic learning experience. I gained practical experience in:
•	Designing and implementing a relational database.
•	Using SQL to create and manage database tables.
•	Establishing and maintaining relationships between different entities in a database.
•	Applying theoretical knowledge to solve real-world problems.

I'm excited to continue building on these skills and look forward to applying them in future projects!

