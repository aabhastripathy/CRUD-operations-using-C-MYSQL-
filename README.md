# CRUD-operations-using-C-MYSQL
 


C++ MySQL CRUD Console Application

This project is a simple command-line interface (CLI) application written in C++ that demonstrates basic CRUD (Create, Read, Update, Delete) operations on a MySQL database. It is intended as a starting template for connecting a C++ application to a relational database.

🛠️ Prerequisites

To compile and run this application, you need the following:

C++ Compiler: A standard C++ compiler (e.g., GCC/G++).

MySQL Server: A running instance of MySQL or MariaDB.

MySQL C Connector: The official C API connector library for MySQL, which allows C/C++ programs to interact with the database server.

Installing the MySQL C Connector

The installation steps vary by operating system:

Windows: Download the MySQL Connector/C from the official MySQL website. You will need to configure your compiler/IDE (like Visual Studio or Code::Blocks) to link against the necessary library files (libmysql.lib or similar) and include the header files.

Linux (Debian/Ubuntu):

sudo apt-get install libmysqlclient-dev


macOS (using Homebrew):

brew install mysql-client


⚙️ Setup and Configuration

1. Database Setup

Before running the application, you must set up the database and table.

Create the Database: Access your MySQL shell or client and create the database named my_db.

CREATE DATABASE my_db;
USE my_db;


Create the Table: Create a table named student with the following schema:

CREATE TABLE student (
    ID INT PRIMARY KEY,
    Name VARCHAR(100),
    Grade FLOAT
);


2. Update Credentials

Open the main.cpp (or equivalent C++ file) and update the database connection constants with your personal MySQL credentials.

// main.cpp snippet
const char* HOST = "localhost";
const char* USER = "root";
const char* PASSWORD = "08520"; // <--- CHANGE THIS TO YOUR ACTUAL PASSWORD!
const char* DB = "my_db";


🚀 Compilation and Execution

Compilation Command

You must link the MySQL connector library when compiling the code.

Example (using g++ on Linux/macOS):

g++ main.cpp -o db_app -lmysqlclient


main.cpp: Your source file name.

-o db_app: The desired name for the executable file.

-lmysqlclient: The flag to link the MySQL C Connector library.

Running the Application

After successful compilation, run the executable:

./db_app


Application Features

The program will connect to MySQL and present a menu allowing you to perform the following operations on the student table:

1. Insert Data: Add a new student record (ID, Name, Grade).

2. Read/View Data: Display all records currently in the student table.

3. Update Data: Modify the grade of an existing student using their ID.

4. Delete Data: Remove a student record using their ID.

0. Exit: Close the application and the database connection.

⚠️ Important Security Note

This example uses direct string concatenation to build SQL queries, which is susceptible to SQL Injection attacks.

For production or secure applications, you MUST use prepared statements (mysql_stmt_init, mysql_stmt_prepare, etc.) to safely bind data and prevent injection vulnerabilities. This current structure is for demonstration purposes only.
<img width="1475" height="760" alt="Screenshot 2025-11-08 000859" src="https://github.com/user-attachments/assets/fc76d4b2-6ebd-4ac0-aed3-b359d8c40aca" />

