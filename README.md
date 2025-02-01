# SQL-basic-to-advance
This Repo contains SQL interview questions along with their answers. Each question is followed by a detailed explanation of the query.

### Table Used for Questions

This table will be referenced for solving SQL questions:

| EmployeeID | Name       | Department  | Salary | JoiningDate | ManagerID |
|------------|------------|-------------|--------|-------------|-----------|
| 1          | Alice      | HR          | 60000  | 2021-05-01  | 3         |
| 2          | Bob        | IT          | 75000  | 2020-08-15  | 3         |
| 3          | Charlie    | Management  | 120000 | 2018-12-01  | NULL      |
| 4          | David      | IT          | 70000  | 2022-01-20  | 2         |
| 5          | Eva        | HR          | 58000  | 2023-03-10  | 1         |

## Question 1: Fetch names of employees in the IT department
### Query:
```sql
SELECT Name 
FROM Employees 
WHERE Department = 'IT';
```
## Explaination :
SELECT Name: Fetches the Name column from the table.

FROM Employees: Indicates the table to query.

WHERE Department = 'IT': Filters the rows where the Department column equals 'IT'

## Question 2: Find the total salary of employees in the HR department
### Query:
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employees
WHERE Department = 'HR';
```
## Explaination :
SUM(Salary): Adds up the values in the Salary column.

AS TotalSalary: Renames the result as TotalSalary.

WHERE Department = 'HR': Filters only the rows where the Department is 'HR'.

## Question 3: Find employees who joined after January 1, 2022
### Query:
```sql
SELECT Name, JoiningDate
FROM Employees
WHERE JoiningDate > '2022-01-01';
```
## Explaination :
WHERE JoiningDate > '2022-01-01': Compares the JoiningDate column to a specific date.

Dates in SQL are compared chronologically, so this will return employees who joined after January 1, 2022.

## Question 4: Count the number of employees under each department
### Query:
```sql
SELECT Department, COUNT(*) AS EmployeeCount
FROM Employees
GROUP BY Department;
```
## Explaination :
COUNT(*): Counts the number of rows (employees) in each group.

GROUP BY Department: Groups the rows by the Department column, so the count is calculated per department.

## Question 5: Find the highest salary in each department
### Query:
```sql
SELECT Department, MAX(Salary) AS HighestSalary
FROM Employees
GROUP BY Department;
```
## Explanation:
MAX(Salary): Finds the highest salary in each department.

GROUP BY Department: Groups the data by department so that MAX(Salary) is calculated per department.

## Question 6: Find the second highest salary in the Employees table
### Query:
```sql
SELECT MAX(Salary) AS SecondHighestSalary 
FROM Employees 
WHERE Salary < (SELECT MAX(Salary) FROM Employees);
```
## Explanation
SELECT MAX(Salary) FROM Employees: Gets the highest salary.

WHERE Salary < (SELECT MAX(Salary) FROM Employees): Filters out the highest salary so that MAX(Salary) now gives the second highest.

## Question 7: Retrieve the department-wise average salary, but only for departments where the average salary is greater than 60,000
### Query:
```sql
SELECT Department, AVG(Salary) AS AverageSalary
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 60000;
```
## Explanation
AVG(Salary): Calculates the average salary per department.

GROUP BY Department: Groups employees by department to calculate separate averages.

HAVING AVG(Salary) > 60000: Filters only departments where the average salary exceeds 60,000.
