# PyQt5 and Tkinter Features

This repository contains implementations of both PyQt5 and Tkinter features.

## Contributors

- **Maya Ali** – Worked extensively on the development and integration of the Tkinter feature.
- **Toufic Al Mabsout** – Developed and implemented the PyQt5 feature, contributing to the modern GUI enhancements.

## Description

### PyQt5 Feature
The PyQt5 feature introduces a modern graphical user interface (GUI) built using PyQt5. This implementation enhances user interaction with the application by offering advanced widgets and a sleek design.

### Tkinter Feature
The Tkinter feature provides a lightweight, easy-to-use GUI interface, designed for simpler use cases. This feature offers a traditional desktop interface for interacting with the application.

## Usage

### Step 1: Set Up Database
1. In the parent directory of your project, create a folder named `Database`.
2. Inside the `Database` folder, create a file named `schoolsystem.sqlite`.

### Step 2: Connect to the Database
3. Connect your database to the `schoolsystem.sqlite` file. We recommend using [SQLiteStudio](https://sqlitestudio.pl/) (v3.4.4) for this purpose.

### Step 3: Create the Database Schema
4. Open the database in SQLiteStudio (or any preferred SQLite management tool), and execute the following SQL queries to create the required tables:

    ```sql
    CREATE TABLE students (
        student_id     VARCHAR(50) PRIMARY KEY,
        name           VARCHAR(100) NOT NULL,
        age            INT,
        email          VARCHAR(100) UNIQUE NOT NULL   
    );

    CREATE TABLE instructors (
        instructor_id  VARCHAR(50) PRIMARY KEY,
        name           VARCHAR(100) NOT NULL,
        age            INT,
        email          VARCHAR(100) UNIQUE NOT NULL
    );

    CREATE TABLE courses (
        course_id      VARCHAR(50) PRIMARY KEY,
        course_name    VARCHAR(100) NOT NULL,
        instructor_id  VARCHAR(50),
        FOREIGN KEY (instructor_id) REFERENCES instructors(instructor_id)
    );

    CREATE TABLE student_courses (
        student_id   VARCHAR(50),
        course_id    VARCHAR(50),
        PRIMARY KEY (student_id, course_id),
        FOREIGN KEY (student_id) REFERENCES students(student_id),
        FOREIGN KEY (course_id) REFERENCES courses(course_id)
    );
    ```

### Step 4: Running the Project
5. After setting up the database, you are ready to run the project. Open the file you want to execute in your IDE and click the run button.

