create database company;
use  company;
create table regions(region_id int primary key,region_name varchar(50));
create table countries(country_id int primary key,country_name varchar(50), region_id int , foreign key(region_id) references regions(region_id));
create table locations(location_id int primary key,street_address varchar(55),postal_code varchar(20),city varchar(20),state_province varchar(30), country_id int,foreign key(country_id) references countries(country_id));
create table departments(department_id int primary key, department_name varchar(55),location_id int, foreign key(location_id) references locations(location_id));
create table dependents(dependent_id int primary key,
    -> first_name varchar(55),
    -> last_name varchar(55),
    -> relationship varchar(55),
    -> employee_id int,
    -> foreign key(employee_id) references employee(employee_id)
    -> );
create table jobs(
    -> job_id int primary key,
    -> job_title varchar(35),
    -> min_salary int,
    -> max_salary int);

CREATE TABLE employee (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(55),
    last_name VARCHAR(55),
    email VARCHAR(55),
    phone_number VARCHAR(15),  
    hire_date DATE,
    job_id INT,
    salary INT,
    manager_id INT,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id),
    FOREIGN KEY (job_id) REFERENCES jobs(job_id)
);


-- Insert dummy data into the regions table
INSERT INTO regions (region_id, region_name) VALUES (1, 'North America');
INSERT INTO regions (region_id, region_name) VALUES (2, 'South America');
INSERT INTO regions (region_id, region_name) VALUES (3, 'Europe');
INSERT INTO regions (region_id, region_name) VALUES (4, 'Asia');
INSERT INTO regions (region_id, region_name) VALUES (5, 'Africa');
INSERT INTO regions (region_id, region_name) VALUES (6, 'Oceania');
INSERT INTO regions (region_id, region_name) VALUES (7, 'Antarctica');

-- Insert dummy data into the countries table
INSERT INTO countries (country_id, country_name, region_id) VALUES (1, 'United States', 1);
INSERT INTO countries (country_id, country_name, region_id) VALUES (2, 'Canada', 1);
INSERT INTO countries (country_id, country_name, region_id) VALUES (3, 'Brazil', 2);
INSERT INTO countries (country_id, country_name, region_id) VALUES (4, 'Argentina', 2);
INSERT INTO countries (country_id, country_name, region_id) VALUES (5, 'Germany', 3);
INSERT INTO countries (country_id, country_name, region_id) VALUES (6, 'France', 3);
INSERT INTO countries (country_id, country_name, region_id) VALUES (7, 'China', 4);
INSERT INTO countries (country_id, country_name, region_id) VALUES (8, 'Japan', 4);
INSERT INTO countries (country_id, country_name, region_id) VALUES (9, 'Nigeria', 5);
INSERT INTO countries (country_id, country_name, region_id) VALUES (10, 'South Africa', 5);
INSERT INTO countries (country_id, country_name, region_id) VALUES (11, 'Australia', 6);
INSERT INTO countries (country_id, country_name, region_id) VALUES (12, 'New Zealand', 6);
INSERT INTO countries (country_id, country_name, region_id) VALUES (13, 'Antarctica', 7); -- Note: This is not a real country but added for completeness
INSERT INTO countries (country_id, country_name, region_id) VALUES (14, 'India', 4);  -- Assuming region_id 4 is for Asia

-- Insert dummy data into the locations table

INSERT INTO locations (location_id, street_address, postal_code, city, state_province, country_id) VALUES 
(1700, '123 Main St', '90210', 'Beverly Hills', 'California', 1),  -- United States
(1701, '456 Maple Ave', 'M5A 1A1', 'Toronto', 'Ontario', 2),      -- Canada
(1702, '789 Elm St', '04567', 'São Paulo', 'São Paulo', 3),        -- Brazil
(1703, '101 Oak Dr', 'C1000AB', 'Amsterdam', 'North Holland', 4),  -- Netherlands
(1704, '202 Pine Ln', '10112', 'Paris', 'Île-de-France', 5),        -- France
(1705, '678 Sunset Blvd', '90028', 'Los Angeles', 'California', 1), -- Los Angeles, United States
(1706, 'Connaught Place', '110001', 'Delhi', 'Delhi', 14);            -- Delhi, India

INSERT INTO jobs (job_id, job_title, min_salary, max_salary) VALUES 
    -> (1, 'Software Engineer', 6000, 12000),    -- Monthly salaries
    -> (2, 'Data Scientist', 7000, 13000),
    -> (3, 'Project Manager', 8000, 15000),
    -> (4, 'UX Designer', 5000, 10000),
    -> (5, 'Product Manager', 7500, 14000),
    -> (6, 'System Analyst', 5500, 10500),
    -> (7, 'Database Administrator', 6500, 12500),
    -> (8, 'Quality Assurance Engineer', 5200, 9500),
    -> (9, 'Manager', 7000, 12000);


INSERT INTO departments (department_id, department_name, location_id) VALUES  (1, 'Human Resources', 1700),(2, 'Information Technology', 1701), (3, 'Marketing', 1702), (4, 'Sales', 1703), (5, 'Finance', 1704), (6, 'Legal', 1706);



-- Insert employees with IDs 101, 102, and 201
INSERT INTO employee (employee_id, first_name, last_name, email, phone_number, hire_date, job_id, salary, manager_id, department_id) VALUES
(101, 'Zach', 'Smith', 'zach.smith@example.com', 9876543210, '2024-01-15', 9, 9000, NULL, 5),   -- Manager in Finance Department
(102, 'Alice', 'Johnson', 'alice.johnson@example.com', 9876543211, '2023-06-22', 8, 7500, 101, 5), -- Employee under Manager Zach
(201, 'Zane', 'Brown', 'zane.brown@example.com', 9876543212, '2024-03-10', 9, 9500, NULL, 5)  -- Manager in Finance Department
(103, 'Amit', 'Kumar', 'amit.kumar@example.com', '9876543210', '2024-02-20', 9, 9100, NULL, 5),   (104, 'Priya', 'Sharma', 'priya.sharma@example.com', '9876543211', '2023-07-15', 8, 7800, 103, 5),  (105, 'Raj', 'Patel', 'raj.patel@example.com', '9876543212', '2024-04-05', 9, 9300, NULL, 5),    (106, 'Neha', 'Singh', 'neha.singh@example.com', '9876543213', '2023-11-11', 8, 8000, 105, 5),  (107, 'Suresh', 'Reddy', 'suresh.reddy@example.com', '9876543214', '2024-05-25', 7, 7000, 101, 5),  (108, 'Sneha', 'Desai', 'sneha.desai@example.com', '9876543215', '2024-06-10', 7, 7100, 105, 5);

-- Insert data into the dependents table
INSERT INTO dependents (dependent_id, first_name, last_name, relationship, employee_id) VALUES
(1, 'Rajesh', 'Kumar', 'Spouse', 102),     -- Dependent for Alice Johnson
(2, 'Sita', 'Johnson', 'Child', 102),       -- Dependent for Alice Johnson
(3, 'Aarav', 'Sharma', 'Child', 104),       -- Dependent for Priya Sharma
(4, 'Aarti', 'Sharma', 'Spouse', 104);      -- Dependent for Priya Sharma

-- Employees without dependents
-- Assuming employee IDs 101 (Zach Smith) and 107 (Suresh Reddy) have no dependents, so no entries for these employees.

SELECT * FROM regions;
SELECT * FROM countries;
SELECT * FROM locations;
SELECT * FROM departments;
SELECT * FROM employee;
SELECT * FROM jobs;
SELECT * FROM dependents;


UPDATE employee
SET department_id = 1
WHERE manager_id IS NULL;



SELECT *
FROM employee e
JOIN departments d ON e.department_id=d.department_id
JOIN locations l ON d.location_id = l.location_id
WHERE l.location_id = 1700;
