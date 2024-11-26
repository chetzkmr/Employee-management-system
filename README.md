# Employee Management System for TechCorp
## Overview

The Employee Management System for TechCorp is designed to efficiently manage employee data, including departments, job titles, personal information, attendance, salaries, and project allocations. This project showcases the database design, normalization, SQL queries, triggers, transactions, string manipulation, and date/time functions necessary to ensure data integrity and effective management.
Features

    Department Management: Store and manage department information.
    Job Title Management: Store and manage job titles for employees.
    Employee Information: Manage employee personal details, hire dates, and departmental associations.
    Attendance Tracking: Track employee attendance with valid status options.
    Salary Management: Store and manage employee salary details, including bonuses and deductions.
    Project Management: Manage projects and project managers.
    Project Allocation: Handle many-to-many relationships between employees and projects.


## Analysis Summary

This project focuses on creating a comprehensive database schema for managing various aspects of employee information in a mid-sized company, TechCorp. The analysis includes:

    Designing normalized tables to avoid data redundancy.
    Ensuring referential integrity through foreign key constraints.
    Implementing various constraints to maintain data accuracy and consistency.
    Writing complex SQL queries to extract meaningful insights from the data.
    Utilizing triggers and transactions to automate and secure database operations.
    Employing string manipulation and date/time functions to handle and analyze data efficiently.

Database Schema

The database schema consists of the following tables:

    Department
        DepartmentID (Primary Key)
        DepartmentName (Not Null)

    JobTitle
        JobTitleID (Primary Key)
        JobTitleName (Not Null, Unique)

    Employee
        EmployeeID (Primary Key)
        FirstName (Not Null)
        LastName (Not Null)
        DateOfBirth
        Gender
        PhoneNumber (Unique)
        Email (Unique)
        HireDate
        DepartmentID (Foreign Key)
        JobTitleID (Foreign Key)
        ManagerID (Self-referencing Foreign Key, Nullable)

    Attendance
        AttendanceID (Primary Key)
        EmployeeID (Foreign Key)
        Date
        Status (Check constraint: 'Present', 'Absent', 'Leave')

    Salary
        SalaryID (Primary Key)
        EmployeeID (Foreign Key)
        BaseSalary (Not Null)
        Bonus (Default 0.00)
        Deduction (Default 0.00)
        PaymentDate

    Project
        ProjectID (Primary Key)
        ProjectName (Not Null)
        StartDate
        EndDate
        ProjectManagerID (Foreign Key)

    ProjectAllocation
        AllocationID (Primary Key)
        EmployeeID (Foreign Key)
        ProjectID (Foreign Key)
        AllocationDate
        Unique constraint on EmployeeID and ProjectID


