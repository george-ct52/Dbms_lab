#LAB CYCLE 1
Experiment No: 1
Familiarization of DDL Commands
Data Definition Language (DDL) - These SQL commands are used for creating, modifying,
and dropping the structure of database objects. The commands are CREATE, ALTER,
DROP, RENAME, and TRUNCATE.
A. Consider the database for a college. Write SQL commands to implement the
following:
1. Create a database
2. Select the current database
3. Create the following tables:
a) Student (roll_no integer, name varchar, dob date, address text,
phone_no varchar, blood_grp varchar)
b) Course (Course_id integer, Course_name varchar, course_duration
integer)
4. List all tables in the current database.
5. Display the structure of the Student table.
6. Drop the column blood_grp from Student table.
7. Add a new column Adar_no with domain number to the table Student.
8. Change the datatype of phone_no from varchar to int
9. Drop the tables.
10. Delete the database.

B. Consider the database for an organization. Write SQL commands to implement the
following:
1. Create a database
2. Select the current database
3. Create the following tables:
a) Employee (emp_no varchar, emp_name varchar, dob date, address
text, mobile_no integer, dept_no varchar, salary integer)
b) Department (dept_no varchar, dept_name varchar, location varchar)
4. List all tables in the current database.
5. Display the structure of the Employee table and Department table.
6. Add a new column ‘Designation’ to the table Employee.
7. Drop the column ‘location’ from Department table.
Experiment No: 2
Familiarization of SQL Constraints.
1. Create new table Persons with attributes PersonID (integer, PRIMARY KEY),
Name (varchar , NOT NULL), Aadhar (Number, NOT NULL, UNIQUE), Age
(integer , CHECK>18).
2. CREATE TABLE Orders with attributes OrderID (PRIMARY KEY),
OrderNumber(NOT NULL) and PersonID( set FOREIGN KEY on attribute
PersonID referencing the column PersonId of Person table)
3. Display the structure of Persons tables.
4. Display the structure of Orders tables.
5. Add emp_no as the primary key of the table Employee.
6. Add dept_no as the primary key of the table Department.
7. Add dept_no in Employee table as the foreign key reference to the table Department
with on delete cascade.
8. Drop the primary key of the table Orders.
Experiment No: 3
Familiarization of DML Commands.
1. Add at least 10 rows into the table Employee and Department.
2. Display all the records from the above tables.
3. Display the emp_no and name of employees from department no ‘D02’.
4. Display emp_no, emp_name , designation, deptno and salary of employees in the
descending order of salary.
5. Display the emp_no , name of employees whose salary is between 2000 and 5000
6. Display the designations without duplicate values
7. Change the salary of employees to 45000 whose designation is 'Manager'
8. Change the mobile number of employees named John
9. Delete all employees whose salary is equal to Rs.7000
10. Retrieve the name, mobile number of all employees whose name start with “A”.
11. Display the details of the employee whose name has at least three characters and
salary greater than 20000.
12. Display the details of employees with empid ‘emp1’, ‘emp2’ and ‘emp6’.
13. Display employee name and employee id of those who have salary between 120000
and 300000.
14. Display the details of employees whose designation is ‘Manager’ or ‘Computer
Assistant’.
15. Displays how many employees work for each department.
16. Displays average salary of employees in each department.
17. Displays total salary of employees in each department.
18. Displays top and lower salary of employees in each department.
19. Displays average salary of employees in all departments except department with
department number ‘D05’.
20. Displays average salary of employees in all departments except department with
department number ‘D01’ and average salary greater than 20000 in the ascending
order of average salary.