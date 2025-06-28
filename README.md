# task03-26-06-2025

## Table: Employees

```
CREATE TABLE Employees (
    EmployeeID INT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Department VARCHAR(50),
    Salary DECIMAL(10, 2),
    JoiningDate DATE
);
```

###  1. Use SELECT * and Specific Columns

```
-- Select all columns
SELECT * FROM Employees;

-- Select specific columns
SELECT FirstName, LastName, Salary FROM Employees;
```

###  2. Apply WHERE, AND, OR, LIKE, BETWEEN

```
-- Use WHERE to filter by department
SELECT * FROM Employees
WHERE Department = 'Engineering';

-- Use WHERE with AND to filter multiple conditions
SELECT * FROM Employees
WHERE Department = 'Engineering' AND Salary > 70000;

-- Use WHERE with OR
SELECT * FROM Employees
WHERE Department = 'HR' OR Department = 'Marketing';

-- Use LIKE to find names starting with 'J'
SELECT * FROM Employees
WHERE FirstName LIKE 'J%';

-- Use BETWEEN to find salaries in a range
SELECT * FROM Employees
WHERE Salary BETWEEN 60000 AND 80000;
```


### 3. Sort with ORDER BY

```
-- Sort by Salary ascending
SELECT * FROM Employees
ORDER BY Salary ASC;

-- Sort by JoiningDate descending
SELECT * FROM Employees
ORDER BY JoiningDate DESC;

-- Combine WHERE and ORDER BY
SELECT FirstName, Department, Salary
FROM Employees
WHERE Salary > 60000
ORDER BY Salary DESC;
```


## Extract Data from Multiple Tables

-- We have another table as follow
```
CREATE TABLE Departments (
    DepartmentName VARCHAR(50),
    Manager VARCHAR(50)
);
```
You can join both:

```
SELECT E.FirstName, E.LastName, E.Department, D.Manager
FROM Employees E
JOIN Departments D ON E.Department = D.DepartmentName;
```



