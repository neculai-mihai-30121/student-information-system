Student Information System

A desktop application built with C# (.NET Framework) and SQL Server that allows students to securely access and manage their academic information, including schedules, grades, optional subjects, reviews, and personal data.

Overview

The Student Information System provides a centralized platform where students can:

Authenticate securely

View their class schedule

Check grades

Manage personal information

Select optional subjects

Leave reviews for professors

View personal notes

The system integrates a Windows Forms UI with a SQL Server database, using structured OOP principles and a clear separation between UI, business logic, and data access layers.

Architecture

The application follows a structured architecture composed of:

Presentation Layer – Windows Forms UI

Business Logic Layer – C# classes handling validation and workflows

Data Access Layer – SQL Server interaction via a DatabaseManager class

Database Layer – Relational SQL database with foreign key constraints

Core Components

Login & Sign-up System

Role-based access (Admin / Professor / Student)

CRUD operations for Students

Schedule management

Grades management

Reviews system

Optional subject selection

Notes system

Database Design

The system automatically generates the database and tables if they do not exist.

Main Tables

Groups

Students

Credentials

Schedules

Professors

Grades

Reviews

OptionalSubjects

Notes

Relationships

Students are linked to:

Groups

Credentials

Grades

Reviews

Optional Subjects

Notes

Foreign key constraints enforce referential integrity.

Each student:

Can select only one optional subject

Can leave one review per professor

Has a single notes entry (with multiple note fields)

Authentication System
Login

Admin and Professor roles with elevated permissions

Students authenticated via database credentials

Credential validation against stored records

Sign-up

Username length validation (8–20 characters)

Password complexity rules:

8–20 characters

At least one special character

At least one digit

Email format validation

Features
Student Features

View personal schedule

View grades

View and manage notes

Select optional subject

Submit professor reviews

Professor Features

View students

Assign grades

Manage academic data

Admin Features

Full CRUD operations on students

Search functionality in DataGridView

Manage system-wide data

Testing & Validation

The system includes multiple validation and safety mechanisms:

Field validation before database operations

Foreign key constraint verification

Prevention of redundant entries:

One notes entry per student

One optional subject per student

One review per professor per student

Account type restrictions (students cannot perform admin actions)

Error handling for invalid credentials

Technologies Used

C# (.NET Framework)

Windows Forms (WinForms)

SQL Server Express

SQL Server Management Studio (SSMS)

ADO.NET

Visual Studio

Setup Instructions
Prerequisites

Visual Studio

SQL Server Express

SQL Server Management Studio

Clone the Repository

git clone https://github.com/your-username/student-information-system.git

Configure Database

Ensure SQL Server Express is running

Update the connection string if necessary

Run the application

The database and tables will be created automatically if they do not exist

Run the Application

Open the solution in Visual Studio

Build the project

Start the application

Example Functionalities

Add / Update / Delete Students

Search students by name

Assign grades

Load students by academic year

Store student photos as VARBINARY(MAX)

Child forms loaded dynamically inside the main form

Security Notes

Input validation implemented for authentication and student registration

Foreign key constraints ensure relational integrity

Role-based UI restrictions

Basic credential validation logic implemented

Passwords are stored as plain text in the current implementation. For production environments, hashing (e.g., BCrypt) should be implemented.

Future Improvements

Implement password hashing & salting

Add logging system

Improve UI/UX design

Migrate to .NET Core / .NET 8

Implement REST API backend

Add unit testing

License

This project is provided for educational and demonstration purposes.
